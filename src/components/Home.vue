<template>
  <div class="blue-grey darken-4" id="container">
    <v-btn
      v-scroll="onScroll"
      v-show="fab"
      fab
      fixed
      bottom
      right
      icon
      target="_blank"
      rounded
      xx-large
      dark
      color="yellow accent-1"
      class="ma-5 up"
      @click="$vuetify.goTo('#proyectos', {offset: 50})"
      >
      <v-icon>mdi-chevron-up-circle</v-icon>
    </v-btn>
    <v-img src="@/assets/fondo.gif" height="100vh" class="img">
    </v-img>
    <v-sheet class="inicio transparent text-center mt-xs-0 mt-md-15" width="100%">
      <h1 class="yellow--text text--accent-1 text-uppercase mt-15 pt-10">
        Pablo Yáñez
      </h1>
      <h3 class="white--text mx-5">
        Desarrollador Front-End
      </h3>
      <v-btn
        target="_blank"
        rounded
        x-large
        dark
        class="mt-5 btn-bg"
        @click="$vuetify.goTo('#proyectos', {offset: 50})"
        >
        <span class="mr-1">Ver proyectos</span>
        <v-icon>mdi-file-code-outline</v-icon>
      </v-btn>
      <!-- <v-col col md="6" cols="12">
      </v-col>
      <v-col col offset-md="1" md="5" cols="12">
        <img class="homeBg mt-n15" src="@/assets/bg.jpg" />
      </v-col> -->
    </v-sheet>
    <v-sheet class="section" id="proyectos" color="transparent" dark>
      <v-row justify="center">
        <h2 class="mt-3 mb-4">
          PROYECTOS
          <v-icon class="d-none d-sm-inline">mdi-file-code-outline</v-icon>
        </h2>
      </v-row>
      <v-slide-group v-model="model" center-active dark class="slides">
        <v-slide-item
          v-for="(project, i) in projects"
          :key="i"
          :value="project.img"
          v-slot:default="{ toggle }"
        >
          <v-card
            class="ma-5 project"
            color="blue-grey darken-4"
            height="370"
            width="300"
            dark
            @click="toggle"
            tile
          >
            <v-list-item-content class="ml-5">
              <v-list-item-title>
                <h3 class="yellow--text text--accent-1">
                  {{ project.title }}
                </h3>
              </v-list-item-title>
              <v-list-item-subtitle class="py-1">{{
                project.description
              }}</v-list-item-subtitle>
            </v-list-item-content>
            <v-img :src="require(`@/assets/${project.img}.png`)"></v-img>
            <v-card-text>
              <v-chip-group
                column class="mt-n2"
              >
                <v-chip v-for="(tool, i) in project.tools" :key="i" color="grey darken-4">{{ tool }}</v-chip>
              </v-chip-group>
            </v-card-text>
            <v-card-actions class="card-actions">
              <v-btn text color="yellow accent-1" :href="project.url.repo" target="_blank">
                Repositorio
              </v-btn>
              <v-btn text color="yellow accent-1" :href="project.url.site" target="_blank">
                Sitio
              </v-btn>
              <v-spacer></v-spacer>
            </v-card-actions>
          </v-card>
        </v-slide-item>
      </v-slide-group>
    </v-sheet>
    <v-sheet class="section" color="transparent" dark>
      <v-row justify="center">
        <h2 class="mt-3">
          CONOCIMIENTOS
          <v-icon class="d-none d-sm-inline">mdi-head-cog-outline</v-icon>
        </h2>
      </v-row>
      <v-row justify="center">
        <v-col class="mt-7 text-center d-sm-none">
          <v-card class="pa-1 ma-2 pb-0" color="yellow accent-1" light>
            <v-icon class="px-2">mdi-language-html5</v-icon>
            <v-icon class="px-2">mdi-language-css3</v-icon>
            <v-icon class="px-2">mdi-language-javascript</v-icon>
            <v-icon class="px-2">mdi-jquery</v-icon>
            <v-icon class="px-2">mdi-sass</v-icon>
            <v-card-text class="mt-n3 pb-2">HTML5 | CSS3 | Javascript | JQuery | Sass</v-card-text>
          </v-card>
          <v-card class="pa-1 ma-2 pb-0" color="deep-purple accent-2">
            <v-icon class="px-2">mdi-bootstrap</v-icon>
            <img src="@/assets/materialize.gif" height="20px" class="mb-n1 px-2">
            <v-card-text class="mt-n3 pb-2">Bootstrap | Materialize</v-card-text>
          </v-card>
          <v-card class="pa-1 ma-2 pb-0" color="teal darken-2">
            <v-icon class="px-2">mdi-vuejs</v-icon>
            <img src="@/assets/vuex.png" height="24px" class="mb-n2 px-2">
            <img src="@/assets/router.png" height="20px" class="mb-n1 px-2">
            <v-card-text class="mt-n3 pb-2">Vue.js | Vuex | Vue Router</v-card-text>
          </v-card>
          <v-card class="pa-1 ma-2 pb-0" color="blue accent-2">
            <v-icon class="px-2">mdi-vuetify</v-icon>
            <img src="@/assets/b-vue.png" height="22px" class="mb-n2 px-2">
            <img src="@/assets/v-material.png" height="15px" class="mb-n1 px-2">
            <img src="@/assets/quasar.png" height="20px" class="mb-n2 px-2">
            <v-card-text class="mt-n3 pb-2">Vuetify | Bootstrap Vue | Vue Material | Quasar</v-card-text>
          </v-card>
          <v-card class="pa-1 ma-2 pb-0" color="deep-orange accent-2">
            <v-icon class="px-2">mdi-git</v-icon>
            <v-icon class="px-2">mdi-github</v-icon>
            <v-icon class="px-2">mdi-npm</v-icon>
            <v-icon class="px-2">mdi-firebase</v-icon>
            <v-card-text class="mt-n3 pb-2">Git | GitHub | npm | Firebase</v-card-text>
          </v-card>
        </v-col>
        <v-col class="mt-7 text-center d-none d-sm-block">
          <v-chip class="pa-5 ma-2 pr-0" light color="yellow accent-1">
            <div class="mr-5">
              <span class="mr-1">HTML5</span>
              <v-icon>mdi-language-html5</v-icon>
            </div>
            <div class="mr-5">
              <span class="mr-1">CSS3</span>
              <v-icon>mdi-language-css3</v-icon>
            </div>
            <div class="mr-5">
              <span class="mr-1">JavaScript</span>
              <v-icon>mdi-language-javascript</v-icon>
            </div>
            <div class="mr-5">
              <span class="mr-1">JQuery</span>
              <v-icon>mdi-jquery</v-icon>
            </div>
            <div class="mr-5">
              <span class="mr-1">Sass</span>
              <v-icon>mdi-sass</v-icon>
            </div>
          </v-chip>
          
          <v-chip class="pa-5 ma-2 pr-0" color="deep-purple accent-2">
            <div class="mr-5">
              <span class="mr-1">Bootstrap</span>
              <v-icon>mdi-bootstrap</v-icon>
            </div>
            <v-chip class="mr-5" color="transparent">
              <span class="mr-1 px-0">Materialize</span>
              <img src="@/assets/materialize.gif" height="20px">
            </v-chip>
          </v-chip>

          <v-chip class="pa-5 ma-2 pr-0" color="teal darken-2">
            <div class="mr-5">
              <span class="mr-1">Vue.js</span>
              <v-icon>mdi-vuejs</v-icon>
            </div>
            <v-chip class="mr-5 px-1" color="transparent">
              <span class="mr-1">Vuex</span>
              <img src="@/assets/vuex.png" height="24px">
            </v-chip>
            <v-chip class="mr-5 px-1" color="transparent">
              <span class="mr-1">Vue Router</span>
              <img src="@/assets/router.png" height="20px">
            </v-chip>
          </v-chip>

          <v-chip class="pa-5 ma-2 pr-0" color="blue accent-2">
            <div class="mr-5">
              <span class="mr-1">Vuetify</span>
              <v-icon>mdi-vuetify</v-icon>
            </div>
            <v-chip class="mr-5 px-1" color="transparent">
              <span class="mr-1">Bootstrap Vue</span>
              <img src="@/assets/b-vue.png" height="20px">
            </v-chip>
            <v-chip class="mr-5 px-1" color="transparent">
              <span class="mr-1">Vue Material</span>
              <img src="@/assets/v-material.png" height="15px">
            </v-chip>
            <v-chip class="mr-5 px-1" color="transparent">
              <span class="mr-1">Quasar</span>
              <img src="@/assets/quasar.png" height="20px">
            </v-chip>
          </v-chip>

          <v-chip class="pa-5 ma-2 pr-0" color="deep-orange accent-2">
            <div class="mr-5">
              <span class="mr-1">Git</span>
              <v-icon>mdi-git</v-icon>
            </div>
            <div class="mr-5">
              <span class="mr-1">GitHub</span>
              <v-icon>mdi-github</v-icon>
            </div>
            <div class="mr-5">
              <span class="mr-1">npm</span>
              <v-icon>mdi-npm</v-icon>
            </div>
            <div class="mr-5">
              <span class="mr-1">Firebase</span>
              <v-icon>mdi-firebase</v-icon>
            </div>
          </v-chip>

        </v-col>
      </v-row>
    </v-sheet>
    <v-sheet class="section acerca" color="transparent" dark>
      <v-row justify="center">
        <h2>
          ACERCA DE MÍ
          <v-icon class="d-none d-sm-inline">mdi-account-details-outline</v-icon>
        </h2>
      </v-row>
      <v-row justify="center">
        <v-col lg="8">
          <v-card class="py-4 px-6 mt-6 mx-5 acerca_mio" tile dark color="blue-grey darken-4">
            <p class="text-md-h5 text-xs-body-2">Hola!, soy <b>Pablo Yáñez</b>, desarrollador Front-End creativo y metódico, egresado de Talento Digital para Chile, con alta motivación por aprender, perfeccionarme y poner en práctica mis conocimientos para aportar al desarrollo de una interfaz de usuario agradable, buscando la forma óptima en la cual resolver los requerimientos del cliente, mediante el análisis, investigación y maquetación de soluciones prácticas.</p>
          </v-card>   
          <div class="text-center">
            <v-btn icon color="white" class="ma-4" href="https://github.com/pabloyanezb" target="_blank">
              <v-icon>mdi-github</v-icon>
            </v-btn>
            <v-btn icon color="blue accent-3" class="ma-4" href="https://www.linkedin.com/in/pabloyanezb/" target="_blank">
              <v-icon>mdi-linkedin</v-icon>
            </v-btn>
            <v-btn icon color="pink accent-2" class="ma-4" @click.prevent="dialog = true">
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
    </v-sheet>
    <v-sheet height="900" color="transparent" dark></v-sheet>

    <v-row justify="center">
      <v-dialog v-model="dialog" persistent max-width="600px">
        <v-form @submit.prevent="send">
          <v-card>
            <v-card-title class="pb-2">
              <h2 class="mx-auto">Contacto</h2>
            </v-card-title>
            <v-card-text class="py-0">
              <v-container class="py-0">
                <v-row>
                  <v-col cols="12" sm="6">
                    <v-text-field label="Nombre" required color="pink accent-2"></v-text-field>
                  </v-col>
                  <v-col cols="12" sm="6">
                    <v-text-field label="Email" required color="pink accent-2"></v-text-field>
                  </v-col>
                  <v-col cols="12">
                    <v-text-field
                      label="Asunto"
                      required
                      color="pink accent-2"
                    ></v-text-field>
                  </v-col>
                  <v-col cols="12">
                    <v-textarea
                      label="Mensaje"
                      rows="4"
                      no-resize
                      required
                      color="pink accent-2"
                    ></v-textarea>
                  </v-col>
                </v-row>
              </v-container>
            </v-card-text>
            <v-card-actions>
              <v-spacer></v-spacer>
              <v-btn color="pink accent-2" text @click="dialog = false">Cancelar</v-btn>
              <v-btn color="pink accent-2" text type="submit" @click="dialog = false">Enviar</v-btn>
            </v-card-actions>
          </v-card>
        </v-form>
      </v-dialog>
    </v-row>
  </div>
</template>

<script>
export default {
  name: "Home",
  methods: {
    onScroll (e) {
      if (typeof window === 'undefined') return
      const top = window.pageYOffset ||   e.target.scrollTop || 0
      this.fab = top > 800
    },
    send () {
      console.log('enviado')
    }
  },
  data: () => ({
    publicPath: process.env.BASE_URL,
    model: null,
    fab: false,
    dialog: false,
    projects: [
      {
        title: "Trivia",
        description: "Juego Quiz con preguntas tipo trivia",
        tools: ['Vue.js', 'Firebase', 'Vuetify', 'Vue Router', 'Vuex'],
        img: "Trivia",
        url: {
          repo: 'https://github.com/pabloyanezb/Trivia',
          site: 'https://triviatrivia.web.app'
        }
      },
      {
        title: "Calcula Tu Consumo",
        description: "Calcula combustible desde A hasta B",
        tools: ['ES6','Google Maps API',  'JQuery', 'Select2'],
        img: "consumo",
        url: {
          repo: 'https://github.com/pabloyanezb/proyecto-final-es6',
          site: 'https://pabloyanezb.github.io/proyecto-final-es6/'
        }
      },
      {
        title: "Space Invaders",
        description: "Inspirado en el videojuego arcade",
        tools: ['Javascript', 'HTML', 'CSS'],
        img: "space-invaders",
        url: {
          repo: 'https://github.com/pabloyanezb/space-invaders',
          site: 'https://pabloyanezb.github.io/space-invaders/'
        }
      },
      {
        title: "Batalla de Github",
        description: "Compara dos usuarios de Github",
        tools: ['Javascript', 'GitHub API', 'Bootstrap', 'HTML', 'CSS'],
        img: "batalla-github",
        url: {
          repo: 'https://github.com/pabloyanezb/batalla-github',
          site: 'https://pabloyanezb.github.io/batalla-github/'
        }
      },
      {
        title: "Practica de Ruteo",
        description: "Ejercicio usando Vue Router",
        tools: ['Vue.js', 'Vue Router', 'Materialize'],
        img: "practica-ruteo",
        url: {
          repo: 'https://github.com/pabloyanezb/practica-ruteo',
          site: 'https://pabloyanezb.github.io/practica-ruteo/'
        }
      },
      {
        title: "Juego del Gato",
        description: "El clásico tres en línea o tic-tac-toe",
        tools: ['JQuery', 'Bootstrap', 'HTML', 'CSS'],
        img: "gato",
        url: {
          repo: 'https://github.com/pabloyanezb/Gato',
          site: 'https://pabloyanezb.github.io/Gato/'
        }
      },
      {
        title: "Pokedex",
        description: "Enciclopedia pokemón usando una API",
        tools: ['PokéAPI', 'Bootstrap', 'JQuery', 'HTML', 'CSS'],
        img: "pokedex",
        url: {
          repo: 'https://github.com/pabloyanezb/Pokedex',
          site: 'https://pabloyanezb.github.io/Pokedex/'
        }
      },
    ],
  }),
};
</script>

<style lang="scss">
.v-application {
  overflow-x: hidden;
  overflow-y: hidden;
}
.inicio {
  position: absolute;
  // top: 0;
  z-index: 8 !important;
}
.img {
  opacity: 0.35;
  position: fixed !important;
  height: 100vh !important;
  width: 100% !important;
  z-index: 1 !important;
  // top: 0;
}
.section {
  top: 110vh;
  height: 100vh;
  position: relative;
  z-index: 2;
}
.acerca {
  height: max-content !important;
}
.project {
  overflow: hidden;
  position: relative;  
  box-shadow: 10px 10px 0px -4px rgba(255, 255, 255, 0.164) !important;
}
.project:hover, .project.v-slide-item--active {
  top: -0.5rem;
}
.card-actions {
  position: absolute;
  bottom: 0;
}
.theme--dark.v-chip--active::before {
  opacity: 0 !important;
}
.theme--dark.v-chip:focus::before {
  opacity: 0 !important;
}
.v-chip-group .v-chip--active {
  color: #FFFFFF !important;
}
.homeBg {
  width: 100%;
}
@import url('https://fonts.googleapis.com/css2?family=Montserrat&display=swap');
// @import url('https://fonts.googleapis.com/css2?family=Open+Sans+Condensed:wght@300&display=swap');
h1 {
  font-family: 'Montserrat', sans-serif;
  font-size: 4rem;
  letter-spacing: 3px;
}
* {
  // font-family: "Open Sans Condensed", sans-serif;
  // font-weight: 600;
  letter-spacing: 1px;
}
h2 {
  font-size: 2rem;
  font-family: 'Montserrat', sans-serif;
}
h3 {
  font-size: 1.5rem;
}
.btn-bg {
  background-size: 200% auto;
  background-image: linear-gradient(
    to right,
    #26a69a 0%,
    #1de9b6 61%,
    #26a69a 100%
  );
  transition: 0.5s;
  color: #FAFAFA !important;
}
.v-btn:hover {
  background-position: right center;
}
.acerca_mio {
  opacity: 0.95;
  // font-size: 1.45rem;
  box-shadow: 10px 10px 0px -4px rgba(255, 255, 255, 0.143) !important;
  b {
    color: #FFFF8D;
  }
}
.v-btn--icon.v-size--default .v-icon, .v-btn--fab.v-size--default .v-icon {
  font-size: 3rem !important;
}
.hide {
  opacity:0;
}
.show {
  opacity:1;
}
</style>
