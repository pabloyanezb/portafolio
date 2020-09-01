<template>
  <div>
    <v-container>
      <v-row class="inicio">
        <v-col col md="6" cols="12">
          <h1
            class="light-blue--text text--accent-2 text-uppercase font-weight-medium mt-15 pt-10"
          >
            {{ title }}
          </h1>
          <h2 class="white--text text-h4 pt-5 mx-5">
            Soy Pablo Yáñez, Desarrollador Front-End
          </h2>
        </v-col>
        <v-col col offset-md="1" md="5" cols="12">
          <img class="homeBg mt-n15" src="@/assets/bg.jpg" />
        </v-col>
      </v-row>
    </v-container>
    <v-sheet class="section" color="blue-grey darken-4">
      <v-parallax src="@/assets/skills.jpg" class="parallax">
        <h1
          class="yellow--text text--accent-1 text-h3 font-weight-medium ml-15"
        >
          {{ proyectos }}
        </h1>
      </v-parallax>
      <v-slide-group v-model="model" center-active dark class="pt-10">
        <v-slide-item
          v-for="(project, i) in projects"
          :key="i"
          :value="project.img"
          v-slot:default="{ toggle }"
        >
          <v-card
            class="ma-4 project"
            height="380"
            width="300"
            @click="toggle"
            dark
            tile
          >
            <v-list-item-content class="ml-5">
              <v-list-item-title class="headline">{{
                project.title
              }}</v-list-item-title>
              <v-list-item-subtitle>{{
                project.description
              }}</v-list-item-subtitle>
            </v-list-item-content>
            <v-img :src="require(`@/assets/${project.img}.png`)"></v-img>
            <v-card-text>
              <v-chip-group
                column
              >
                <v-chip v-for="(tool, i) in project.tools" :key="i" color="blue-grey darken-3">{{ tool }}</v-chip>
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
    <v-sheet class="section" color="grey darken-4">
      <v-parallax src="@/assets/skills.jpg" class="parallax">
        <h1
          class="yellow--text text--accent-1 text-h3 font-weight-medium ml-15"
        >
          {{ skills }}
        </h1>
      </v-parallax>
    </v-sheet>
    <v-sheet class="section" color="blue-grey darken-4">
      <v-parallax src="@/assets/skills.jpg" class="parallax">
        <h1
          class="yellow--text text--accent-1 text-h3 font-weight-medium ml-15"
        >
          {{ acerca_mio }}
        </h1>
      </v-parallax>
    </v-sheet>
    <v-sheet class="section" color="grey darken-4">
      <v-parallax src="@/assets/skills.jpg" class="parallax">
        <h1
          class="yellow--text text--accent-1 text-h3 font-weight-medium ml-15"
        >
          {{ contacto }}
        </h1>
      </v-parallax>
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
    proyectos: '< Proyectos />',
    skills: '< Skills />',
    acerca_mio: '< Acerca de Mí />',
    contacto: '< Contacto />',
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

<style>
.inicio {
  position: fixed;
  height: 100vh;
  z-index: 1;
}
.section {
  top: 100vh;
  height: 92vh;
  position: relative;
  z-index: 2 !important;
}
.project {
  overflow: hidden;
  position: relative;
  box-shadow: 10px 10px 0px -4px #37474F !important;
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
@import url("https://fonts.googleapis.com/css2?family=Roboto+Condensed:wght@700&display=swap");
h1 {
  font-family: "Roboto Condensed", sans-serif;
  font-size: 50pt;
}
.parallax {
  height: 100px !important;
}
</style>
