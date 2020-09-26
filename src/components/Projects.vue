<template>
  <v-sheet class="section" id="proyectos" color="transparent" dark>
    <v-row justify="center">
      <h2 class="mt-3 mb-4 pt-3">
        PROYECTOS
        <v-icon class="d-none d-sm-inline">mdi-file-code-outline</v-icon>
      </h2>
    </v-row>
    <v-slide-group v-model="model" center-active dark>
      <v-slide-item
        v-for="(project, i) in projects"
        :key="i"
        :value="project.img"
      >
        <v-card
          class="ma-5 project"
          color="blue-grey darken-4"
          height="370"
          width="300"
          dark
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
          <v-img :src="require(`@/assets/${project.img}.png`)" :lazy-src="require(`@/assets/lazy.png`)"></v-img>
          <v-card-text>
            <v-chip-group column class="mt-n2">
              <v-chip
                v-for="(tool, i) in project.tools"
                :key="i"
                color="grey darken-4"
                >{{ tool }}</v-chip
              >
            </v-chip-group>
          </v-card-text>
          <v-card-actions class="card-actions">
            <v-btn
              text
              color="yellow accent-1"
              :href="project.url.repo"
              target="_blank"
            >
              Repositorio
            </v-btn>
            <v-btn
              text
              color="yellow accent-1"
              :href="project.url.site"
              target="_blank"
            >
              Sitio
            </v-btn>
            <v-spacer></v-spacer>
          </v-card-actions>
        </v-card>
      </v-slide-item>
    </v-slide-group>
    <p class="d-lg-none mt-n1 text-center caption">Desliza para ver más proyectos >></p>
  </v-sheet>
</template>

<script>
export default {
  name: "Projects",
  data: () => ({
    model: null,
    projects: [
      {
        title: "Portafolio",
        description: "Portafolio hecho en Vue.js",
        tools: ["Vue.js", "Vuetify", "EmailJS"],
        img: "portfolio",
        url: {
          repo: "https://github.com/pabloyanezb/portafolio",
          site: "https://pabloyanezb.github.io/portafolio/",
        },
      },
      {
        title: "Trivia",
        description: "Juego Quiz con preguntas tipo trivia",
        tools: ["Vue.js", "Firebase", "Vuetify", "Vue Router", "Vuex"],
        img: "Trivia",
        url: {
          repo: "https://github.com/pabloyanezb/Trivia",
          site: "https://triviatrivia.web.app",
        },
      },
      {
        title: "Space Invaders",
        description: "Inspirado en el videojuego arcade",
        tools: ["Javascript", "HTML", "CSS"],
        img: "space-invaders",
        url: {
          repo: "https://github.com/pabloyanezb/space-invaders",
          site: "https://pabloyanezb.github.io/space-invaders/",
        },
      },
      {
        title: "Batalla de Github",
        description: "Compara dos usuarios de Github",
        tools: ["Vue.js", "GitHub API", "Bootstrap", "HTML", "CSS"],
        img: "batalla-github",
        url: {
          repo: "https://github.com/pabloyanezb/batalla-github",
          site: "https://pabloyanezb.github.io/batalla-github/",
        },
      },
      {
        title: "Calcula Tu Consumo",
        description: "Calcula combustible desde A hasta B",
        tools: ["ES6", "Google Maps API", "JQuery", "Select2"],
        img: "consumo",
        url: {
          repo: "https://github.com/pabloyanezb/proyecto-final-es6",
          site: "https://pabloyanezb.github.io/proyecto-final-es6/",
        },
      },
      {
        title: "Practica de Ruteo",
        description: "Ejercicio usando Vue Router",
        tools: ["Vue.js", "Vue Router", "Materialize"],
        img: "practica-ruteo",
        url: {
          repo: "https://github.com/pabloyanezb/practica-ruteo",
          site: "https://pabloyanezb.github.io/practica-ruteo/",
        },
      },
      {
        title: "Juego del Gato",
        description: "El clásico tres en línea o tic-tac-toe",
        tools: ["JQuery", "Bootstrap", "HTML", "CSS"],
        img: "gato",
        url: {
          repo: "https://github.com/pabloyanezb/Gato",
          site: "https://pabloyanezb.github.io/Gato/",
        },
      },
      {
        title: "Pokedex",
        description: "Enciclopedia Pokémon usando API",
        tools: ["PokéAPI", "Bootstrap", "JQuery", "HTML", "CSS"],
        img: "pokedex",
        url: {
          repo: "https://github.com/pabloyanezb/Pokedex",
          site: "https://pabloyanezb.github.io/Pokedex/",
        },
      },
    ],
  }),
}
</script>

<style>
.project {
  overflow: hidden;
  position: relative;
  /* box-shadow: 10px 10px 0px -4px rgba(255, 255, 255, 0.164) !important; */
}
.project:hover,
.project.v-slide-item--active {
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
  color: #ffffff !important;
}
.v-chip--clickable {
  cursor: default !important;
}
.v-chip:before {
  background-color: transparent !important;
}
</style>