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
    <v-sheet class="section" color="grey lighten-4">
      <h1 class="amber--text text--accent-3 text-h3 font-weight-medium ml-15 pt-13">
        Proyectos
      </h1>
      <v-slide-group v-model="model" class="pa-4" show-arrows center-active>
        <v-slide-item v-for="(project, i) in projects" :key="i" v-slot:default="{ active, toggle }">
          <v-card
            :color="active ? 'primary' : 'grey lighten-1'"
            class="ma-4 project"
            height="200"
            width="400"
            @click="toggle"
          >
            <v-img :src="require(`@/assets/${project.img}.png`)"/>
            <v-row class="fill-height" align="center" justify="center">
              <v-scale-transition>
                <v-icon
                  v-if="active"
                  color="white"
                  size="48"
                  v-text="'mdi-close-circle-outline'"
                ></v-icon>
              </v-scale-transition>
            </v-row>
          </v-card>
        </v-slide-item>
      </v-slide-group>
      <v-expand-transition>
        <v-sheet
          v-if="model != null"
          color="grey lighten-4"
          height="200"
          tile
        >
          <v-row
            class="fill-height"
            align="center"
            justify="center"
          >
            <h3 class="title">Selected {{ model }}</h3>
          </v-row>
        </v-sheet>
      </v-expand-transition>
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
      {img: 'consumo',},
      {img: 'gato',},
      {img: 'space-invaders',},
      {img: 'pokedex',},
    ]
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
  top: 96vh;
  height: 96vh;
  position: relative;
  z-index: 2 !important;
}
.project {
  overflow: hidden;
}
.homeBg {
  width: 100%;
}
@import url("https://fonts.googleapis.com/css2?family=Roboto+Condensed:wght@700&display=swap");
h1 {
  font-family: "Roboto Condensed", sans-serif;
  font-size: 50pt;
}
</style>
