<template>
  <v-container fluid class="pa-0">
    <v-layout row wrap>
      <v-flex xs12 class="py-2">
        <h2>時計機能 | v-time-picker</h2>
        <v-divider></v-divider>
      </v-flex>

      <v-flex xs12 class="py-2">
        <v-time-picker
          v-model="time"
          type="month"
          width="290"
          class="mt-3"
        ></v-time-picker>
        <v-time-picker
          v-model="time"
          full-width
          landscape
          type="month"
          class="mt-3"
        ></v-time-picker>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<style scoped>
h2 {
  text-align:center;
  margin-top:40px;
  background-color:#B2EBF2;
}
</style>