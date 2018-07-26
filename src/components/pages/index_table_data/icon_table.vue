<template>
  <v-data-table
    :headers="headers"
    :items="icon_list"
    hide-actions
    class="elevation-1" 
    hide-headers="true"
  >
    <template slot="items" slot-scope="props">

      <td v-if="props.item.num == 1">
        <v-btn flat>Flat</v-btn>
      </td>
      <td v-else-if="props.item.num == 2">
        <v-btn>Raised</v-btn>
      </td>
      

      <td>
        <a :href="props.item.url" target="_blank">
          {{ props.item.name }}
        </a>
      </td>
      <td>{{ props.item.text }}</td>
    </template>
  </v-data-table>
</template>

<script>

  export default {
    data () {
      return {
      
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

<style scoped>
h2 {
  text-align:center;
  margin-top:40px;
  background-color:#B2EBF2;
}

table{
  border:solid 1px #ddd;
  width:100%;
}

td{
  border:solid 1px #ddd;
}
</style>
