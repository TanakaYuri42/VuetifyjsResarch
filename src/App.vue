<template>
  <v-app>
    <v-toolbar dark color="cyan lighten-3">
      <v-toolbar-side-icon></v-toolbar-side-icon>
      <v-toolbar-title class="white--text">Menu</v-toolbar-title>
      <v-spacer></v-spacer>

      <v-menu bottom left> 
        <v-btn slot="activator" dark icon>
          <v-icon>fas fa-list</v-icon>
        </v-btn>
      </v-menu>
    </v-toolbar>

    <v-content>
      <HelloWorld/>
      <test/>
    </v-content>

    <v-footer :fixed="fixed" app>
      <span>&copy; 2017</span>
    </v-footer>
  </v-app>
</template>

<script>
import HelloWorld from './components/HelloWorld'
import Test from './components/test'

export default {
  name: 'App',
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
