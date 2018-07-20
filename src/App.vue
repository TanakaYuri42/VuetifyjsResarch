<template>
  <v-container>
    <v-toolbar dark color="cyan lighten-3">
      <v-spacer></v-spacer>
      <v-toolbar-title color="red">Vuetifyのcomponents紹介</v-toolbar-title>
    </v-toolbar>

    <v-content>
      <!-- <HelloWorld/> -->
      <test/>
    </v-content>

    <v-footer height="auto" color="grey darken-3" :fixed="fixed" app>
      <v-layout row wrap>
        <span>&copy; 2018</span>
      </v-layout>
    </v-footer>
  </v-container>
</template>

<script>
import HelloWorld from './components/HelloWorld'
import Test from './components/pages/test'
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
