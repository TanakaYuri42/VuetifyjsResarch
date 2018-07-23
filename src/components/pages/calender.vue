<template>
  <v-layout row wrap>
    <v-flex xs12 sm12 class="py-2">
      <h2>カレンダー | v-date-picker</h2>   
      <v-divider></v-divider>
    </v-flex>

    <v-flex xs12 sm6>
      <v-date-picker v-model="picker" color="green lighten-1"></v-date-picker>
    </v-flex>
    <v-flex xs12 sm6 class="hidden-xs-only">
      ※画面サイズを小さくすると消えます(class="hidden-xs-only")
      <v-date-picker v-model="picker2" color="green lighten-1" header-color="primary"></v-date-picker>
    </v-flex>
  </v-layout>
</template>

<script>
  export default {
    data () {
      return {
        picker: null,
        picker2: null
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
