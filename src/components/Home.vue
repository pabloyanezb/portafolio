<template>
  <div class="blue-grey darken-4">
      <v-img src="@/assets/fondo.gif" height="100vh" class="img">
      </v-img>
      <v-sheet class="inicio transparent text-center mt-15" width="100%">
        <h1 class="yellow--text text--accent-1 text-uppercase mt-15 pt-10">
          Pablo Yáñez
        </h1>
        <h3 class="white--text mx-5">
          Desarrollador Front-End
        </h3>
        <v-btn
          href="https://github.com/vuetifyjs/vuetify/releases/latest"
          target="_blank"
          rounded
          x-large
          dark
          class="mt-5 jugar"
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
    <v-sheet class="section" color="transparent" dark>
      <v-row justify="center">
        <h2 class="mt-3">
          PROYECTOS
          <v-icon>mdi-file-code-outline</v-icon>
        </h2>
      </v-row>
      <v-slide-group v-model="model" center-active dark>
        <v-slide-item
          v-for="(project, i) in projects"
          :key="i"
          :value="project.img"
          v-slot:default="{ toggle }"
        >
          <v-card
            class="ma-5 project"
            color="blue-grey darken-4"
            height="390"
            width="350"
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
              <v-list-item-subtitle>{{
                project.description
              }}</v-list-item-subtitle>
            </v-list-item-content>
            <v-img :src="require(`@/assets/${project.img}.png`)"></v-img>
            <v-card-text>
              <v-chip-group
                column
              >
                <v-chip v-for="(tool, i) in project.tools" :key="i" color="grey darken-4">{{ tool }}</v-chip>
              </v-chip-group>
            </v-card-text>
            <v-card-actions class="card-actions">
              <v-btn text color="yellow accent-1">
                Repositorio
              </v-btn>
              <v-btn text color="yellow accent-1">
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
          SKILLS
          <v-icon>mdi-head-cog-outline</v-icon>
        </h2>
      </v-row>
      <v-container class="mt-7">
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
      </v-container>
    </v-sheet>
    <v-sheet class="section" color="transparent" dark>
      <v-row justify="center">
        <h2 class="mt-3">
          ACERCA DE MÍ
          <v-icon>mdi-account-details-outline</v-icon>
        </h2>
      </v-row>
    </v-sheet>
    <v-sheet class="section" color="transparent" dark>
      <v-row justify="center">
        <h2 class="mt-3">
          CONTACTO
          <v-icon>mdi-email-outline</v-icon>
        </h2>
      </v-row>
    </v-sheet>
    <v-sheet class="section" color="transparent" dark>
    </v-sheet>
  </div>
</template>

<script>
export default {
  name: "Home",
  props: {
    title: String,
  },
  data: () => ({
    model: null,
    projects: [
      {
        title: "Trivia",
        description: "Juego Quiz con preguntas tipo trivia",
        tools: ['Vue.js', 'Firebase', 'Vuetify', 'Vue Router', 'Vuex'],
        img: "Trivia",
      },
      {
        title: "Calcula Tu Consumo",
        description: "Calcula combustible desde A hasta B",
        tools: ['ES6','Google Maps API',  'JQuery', 'Select2'],
        img: "consumo",
      },
      {
        title: "Space Invaders",
        description: "Inspirado en el videojuego arcade",
        tools: ['Javascript', 'HTML', 'CSS'],
        img: "space-invaders",
      },
      {
        title: "Batalla de Github",
        description: "Compara dos usuarios de Github",
        tools: ['Javascript', 'GitHub API', 'Bootstrap', 'HTML', 'CSS'],
        img: "batalla-github",
      },
      {
        title: "Practica de Ruteo",
        description: "Ejercicio usando Vue Router",
        tools: ['Vue.js', 'Vue Router', 'Materialize'],
        img: "practica-ruteo",
      },
      {
        title: "Juego del Gato",
        description: "El clásico tres en línea o tic-tac-toe",
        tools: ['JQuery', 'Bootstrap', 'HTML', 'CSS'],
        img: "gato",
      },
      {
        title: "Pokedex",
        description: "Enciclopedia pokemón usando una API",
        tools: ['PokéAPI', 'Bootstrap', 'JQuery', 'HTML', 'CSS'],
        img: "pokedex",
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
  z-index: 2 !important;
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
  z-index: 2 !important;
}
.project {
  overflow: hidden;
  position: relative;
  box-shadow: 10px 10px 0px -4px rgba(0, 0, 0, 0.465) !important;
  
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
@import url('https://fonts.googleapis.com/css2?family=Open+Sans+Condensed:wght@300&display=swap');
h1 {
  font-family: 'Montserrat', sans-serif;
  font-size: 4rem;
  letter-spacing: 3px;
}
* {
  font-family: "Open Sans Condensed", sans-serif;
  font-weight: 600;
  letter-spacing: 1px;
}
h2 {
  font-size: 2rem;
  font-family: 'Montserrat', sans-serif;
}
h3 {
  font-size: 1.5rem;
}
.jugar {
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
</style>
