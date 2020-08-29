<template>
  <v-app>
    <v-app-bar
      app
      elevation="0"
      dark
    >
      <v-btn
        href=""
        target="_blank"
        text
      >
        <v-icon>mdi-home</v-icon>
        <span class="ml-2">Pablo Yáñez Barriga</span>
      </v-btn>

      <v-spacer></v-spacer>

      <v-btn
        href="https://github.com/vuetifyjs/vuetify/releases/latest"
        target="_blank"
        text
      >
        <span class="mr-2">Proyectos</span>
        <v-icon>mdi-file-code-outline</v-icon>
      </v-btn>
      <v-btn
        href="https://github.com/vuetifyjs/vuetify/releases/latest"
        target="_blank"
        text
      >
        <span class="mr-2">Skills</span>
        <v-icon>mdi-head-cog-outline</v-icon>
      </v-btn>
      <v-btn
        href="https://github.com/vuetifyjs/vuetify/releases/latest"
        target="_blank"
        text
      >
        <span class="mr-2">Acerca de mí</span>
        <v-icon>mdi-account-details-outline</v-icon>
      </v-btn>
      <v-btn
        href="https://github.com/vuetifyjs/vuetify/releases/latest"
        target="_blank"
        text
      >
        <span class="mr-2">Contacto</span>
        <v-icon>mdi-email-outline</v-icon>
      </v-btn>
    </v-app-bar>

    <v-main>
      <Home title="< Hola Mundo! />"/>
    </v-main>
  </v-app>
</template>

<script>
import Home from './components/Home';

export default {
  name: 'App',

  components: {
    Home,
  },

  data: () => ({
    //
  }),
};
</script>

<style lang="scss">
.theme--light.v-application {
  background-color: rgb(21, 21, 21) !important;
}
.v-toolbar {
  background-color: rgb(21, 21, 21) !important;
}
.v-btn:hover {
  span {
   color: #FFFF8D
  }
}
</style>
