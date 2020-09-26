<template>
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
          <img
            src="@/assets/materialize.png"
            height="20px"
            class="mb-n1 px-2"
          />
          <v-card-text class="mt-n3 pb-2" >Bootstrap | Materialize</v-card-text>
        </v-card>
        <v-card class="pa-1 ma-2 pb-0" color="teal darken-2">
          <v-icon class="px-2">mdi-vuejs</v-icon>
          <img src="@/assets/vuex.png" height="24px" class="mb-n2 px-2" />
          <img src="@/assets/router.png" height="20px" class="mb-n1 px-2" />
          <v-card-text class="mt-n3 pb-2">Vue.js | Vuex | Vue Router</v-card-text>
        </v-card>
        <v-card class="pa-1 ma-2 pb-0" color="blue accent-2">
          <v-icon class="px-2">mdi-vuetify</v-icon>
          <img src="@/assets/b-vue.png" height="22px" class="mb-n2 px-2" />
          <img
            src="@/assets/v-material.png"
            height="15px"
            class="mb-n1 px-2"
          />
          <img src="@/assets/quasar.png" height="20px" class="mb-n2 px-2" />
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
            <img src="@/assets/materialize.png" height="20px" />
          </v-chip>
        </v-chip>

        <v-chip class="pa-5 ma-2 pr-0" color="teal darken-2">
          <div class="mr-5">
            <span class="mr-1">Vue.js</span>
            <v-icon>mdi-vuejs</v-icon>
          </div>
          <v-chip class="mr-5 px-1" color="transparent">
            <span class="mr-1">Vuex</span>
            <img src="@/assets/vuex.png" height="24px" />
          </v-chip>
          <v-chip class="mr-5 px-1" color="transparent">
            <span class="mr-1">Vue Router</span>
            <img src="@/assets/router.png" height="20px" />
          </v-chip>
        </v-chip>

        <v-chip class="pa-5 ma-2 pr-0" color="blue accent-2">
          <div class="mr-5">
            <span class="mr-1">Vuetify</span>
            <v-icon>mdi-vuetify</v-icon>
          </div>
          <v-chip class="mr-5 px-1" color="transparent">
            <span class="mr-1">Bootstrap Vue</span>
            <img src="@/assets/b-vue.png" height="20px" />
          </v-chip>
          <v-chip class="mr-5 px-1" color="transparent">
            <span class="mr-1">Vue Material</span>
            <img src="@/assets/v-material.png" height="15px" />
          </v-chip>
          <v-chip class="mr-5 px-1" color="transparent">
            <span class="mr-1">Quasar</span>
            <img src="@/assets/quasar.png" height="20px" />
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
</template>

<script>
export default {
  name: "Skills"
}
</script>

<style>

</style>