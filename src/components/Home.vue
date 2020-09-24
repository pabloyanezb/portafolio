<template>
  <div class="blue-grey darken-4">
    <v-img src="@/assets/fondo.gif" height="100vh" class="fondo"> </v-img>
    <v-sheet
      class="inicio transparent text-center mt-xs-0 mt-md-15"
      width="100%"
    >
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
        @click="$vuetify.goTo('#proyectos', { offset: 50 })"
      >
        <span class="mr-1">Ver proyectos</span>
        <v-icon>mdi-file-code-outline</v-icon>
      </v-btn>
    </v-sheet>

    <Projects></Projects>
    <Skills></Skills>
    <About></About>

    <v-sheet height="115vh" color="transparent" dark class="d-sm-none"></v-sheet>
    <v-sheet height="135vh" color="transparent" dark class="d-none d-sm-block"></v-sheet>


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
      class="up"
      @click="$vuetify.goTo('#proyectos', { offset: 50 })"
    >
      <v-icon>mdi-chevron-up-circle</v-icon>
    </v-btn>
  </div>
</template>

<script>
import Projects from './Projects'
import Skills from './Skills'
import About from './About'

export default {
  name: "Home",
  components: {
    Projects, 
    Skills, 
    About,
  },
  methods: {
    onScroll(e) {
      if (typeof window === "undefined") return;
      const top = window.pageYOffset || e.target.scrollTop || 0;
      this.fab = top > 800;
    },
  },
  data: () => ({
    fab: false,
  }),
};
</script>

<style lang="scss">
.v-application {
  overflow-x: hidden;
  overflow-y: hidden;
}
@import url("https://fonts.googleapis.com/css2?family=Montserrat&display=swap");
* {
  letter-spacing: 1px;
}
h1 {
  font-family: "Montserrat", sans-serif;
  font-size: 4rem;
  letter-spacing: 3px;
}
h2 {
  font-size: 2rem;
  font-family: "Montserrat", sans-serif;
}
h3 {
  font-size: 1.5rem;
}

.inicio {
  position: absolute;
  z-index: 8 !important;
}
.fondo {
  opacity: 0.35;
  position: fixed !important;
  height: 100vh !important;
  width: 100% !important;
  z-index: 1 !important;
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
  color: #fafafa !important;
}
.v-btn:hover {
  background-position: right center;
}
.section {
  top: 110vh;
  height: 100vh;
  position: relative;
  z-index: 2;
}
.v-btn--icon.v-size--default .v-icon,
.v-btn--fab.v-size--default .v-icon {
  font-size: 3rem !important;
}
.hide {
  opacity: 0;
}
.show {
  opacity: 1;
}
</style>
