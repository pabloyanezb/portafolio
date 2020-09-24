<template>
  <v-sheet class="section acerca" color="transparent" dark>
    <v-row justify="center">
      <h2>
        ACERCA DE MÍ
        <v-icon class="d-none d-sm-inline"
          >mdi-account-details-outline</v-icon>
      </h2>
    </v-row>
    <v-row justify="center">
      <v-col lg="8">
        <v-card
          class="py-4 px-6 mt-6 mx-5 acerca_mio"
          tile
          dark
          color="blue-grey darken-4"
        >
          <p class="text-md-h5 text-xs-body-2">
            Hola!, soy <b>Pablo Yáñez</b>, desarrollador Front-End 
            egresado de Talento Digital para Chile, con alta
            motivación por aprender, perfeccionarme y poner en práctica mis
            conocimientos para el desarrollo de una interfaz de
            usuario agradable, buscando la forma óptima en la cual resolver
            los requerimientos del cliente, mediante el análisis,
            investigación y maquetación de soluciones prácticas.
          </p>
        </v-card>
        <div class="text-center">
          <v-btn
            icon
            color="white"
            class="ma-4"
            href="https://github.com/pabloyanezb"
            target="_blank"
          >
            <v-icon>mdi-github</v-icon>
          </v-btn>
          <v-btn
            icon
            color="blue accent-3"
            class="ma-4"
            href="https://www.linkedin.com/in/pabloyanezb/"
            target="_blank"
          >
            <v-icon>mdi-linkedin</v-icon>
          </v-btn>
          <v-btn
            icon
            color="pink accent-2"
            class="ma-4"
            @click.prevent="dialog = true"
          >
            <v-icon>mdi-email-outline</v-icon>
          </v-btn>
          <v-btn
            :href="`${publicPath}cv_pabloyanez.docx`"
            download
            rounded
            large
            dark
            class="btn-bg ml-sm-15 mt-1"
          >
            <span class="mr-1">Descargar CV</span>
            <v-icon>mdi-file-document-outline</v-icon>
          </v-btn>
        </div>
      </v-col>
    </v-row>

    <!-- Modal para contactar, con un formulario para enviar un mensaje a través de emailjs -->
    <v-row justify="center">
      <v-dialog v-model="dialog" persistent max-width="600px">
        <v-form v-model="valid" @submit.prevent="send" ref="form">
          <v-card>
            <v-card-title class="pb-2">
              <h2 class="mx-auto">Contacto</h2>
            </v-card-title>
            <v-card-text class="py-0">
              <v-container class="py-0">
                <v-row>
                  <v-col cols="12" sm="6">
                    <v-text-field
                      label="Nombre"
                      required
                      :rules="[v => !!v || 'Debes ingresar un nombre']"
                      color="pink accent-2"
                      name="user_name"
                    ></v-text-field>
                  </v-col>
                  <v-col cols="12" sm="6">
                    <v-text-field
                      label="Email"
                      required
                      :rules="[v => !!v || 'Debes ingresar un Email', v => /.+@.+/.test(v) || 'E-mail no válido']"
                      color="pink accent-2"
                      name="user_email"
                    ></v-text-field>
                  </v-col>
                  <v-col cols="12">
                    <v-textarea
                      label="Mensaje"
                      rows="4"
                      no-resize
                      counter
                      required
                      :rules="[v => !!v || 'Debes ingresar un Mensaje', v => (v && v.length >= 35) || 'Tu mensaje es demasiado corto']"
                      color="pink accent-2"
                      name="message"
                    ></v-textarea>
                  </v-col>
                </v-row>
              </v-container>
            </v-card-text>
            <v-card-actions>
              <v-spacer></v-spacer>
              <v-btn 
                color="pink accent-2"
                text
                @click="dialog = false, $refs.form.reset()"
                >Cancelar</v-btn>
              <v-btn
                color="pink accent-2"
                text
                type="submit"
                value="Send"
                :disabled="!valid"
                @click="dialog = false"
                >Enviar</v-btn>
            </v-card-actions>
          </v-card>
        </v-form>
      </v-dialog>
    </v-row>

    <!-- Notifica si el mensaje fué enviado -->
    <v-snackbar
      v-model="snackbar"
      :timeout="timeout"
      color="blue-grey darken-4"
      elevation="15"
    >
      Se ha enviado un correo con tu mensaje

      <template v-slot:action="{ attrs }">
        <v-btn
          color="yellow accent-1"
          text
          v-bind="attrs"
          @click="snackbar = false"
        >
          Close
        </v-btn>
      </template>
    </v-snackbar>
  </v-sheet>
</template>

<script>
import emailjs from "emailjs-com";
import { init } from "emailjs-com";
init("user_pQTuEf4Q4hPfVrzMCK2p0");

export default {
  name: "About",
  data: () => ({
    publicPath: process.env.BASE_URL,
    dialog: false,
    valid: false,
    snackbar: false,
    timeout: 2500,
  }),
  methods: {
    send(e) {
      emailjs
        .sendForm(
          "service_gubrv9r",
          "template_qta8ggl",
          e.target,
          "user_pQTuEf4Q4hPfVrzMCK2p0"
        )
        .then(
          (result) => {
            console.log("SUCCESS!", result.status, result.text);
            this.$refs.form.reset();
            this.snackbar = 'true';
          },
          (error) => {
            console.log("FAILED...", error);
          }
        );
    },
  }
}
</script>

<style lang="scss">
.acerca {
  height: max-content !important;
}
.acerca_mio {
  opacity: 0.95;
  // box-shadow: 10px 10px 0px -4px rgba(255, 255, 255, 0.143) !important;
  b {
    color: #ffff8d;
  }
}
</style>