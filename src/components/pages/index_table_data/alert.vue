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

      </td>
      <td v-else-if="props.item.num == 2">
        	
      </td>
      <td v-else-if="props.item.num == 3">
        
      </td>
      <td v-else-if="props.item.num == 4">
        
      </td>
      <td v-else-if="props.item.num == 5">
        
      </td>
      <td v-else-if="props.item.num == 6">
        
      </td>
      <td v-if="props.item.num == 7">

      </td>
      <td v-else-if="props.item.num == 8">
        	
      </td>
      <td v-else-if="props.item.num == 9">
        
      </td>
      <td v-else-if="props.item.num == 10">
        
      </td>
      <td v-else-if="props.item.num == 11">
        
      </td>
      <td v-else-if="props.item.num == 12">
        
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
