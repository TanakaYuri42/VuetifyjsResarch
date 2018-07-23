<template>
  <v-app>
    <v-toolbar dark color="cyan lighten-3">
      <v-spacer></v-spacer>
      <v-toolbar-title>Vuetifyのcomponents紹介</v-toolbar-title>
    </v-toolbar>

    <v-content>
      <v-container fuild>
        <!-- <HelloWorld/> -->
        <test/>
      </v-container>
    </v-content>

    <v-footer height="auto" color="grey darken-3" :fixed="fixed" app>
      <v-layout row wrap>
        <span>&copy; 2018</span>
      </v-layout>
    </v-footer>
  </v-app>
</template>

<script>
import HelloWorld from './components/HelloWorld'
import Test from './components/test'
import router from './components/router'

export default {
  name: 'App',
  router,
  components: {
    HelloWorld,
    Test
  },
  data () {
    return {
      clipped: false,
      drawer: true,
      fixed: false,
      items: [{
        icon: 'bubble_chart',
        title: 'Inspire'
      }],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'Vuetify.js'
    }
  }
}
</script>

<style scoped>
h2 {
  text-align:center;
  margin-top:40px;
  background-color:#B2EBF2;
}
</style>
