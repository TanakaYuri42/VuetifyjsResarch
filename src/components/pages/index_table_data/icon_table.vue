<template>
  <v-data-table
    :headers="headers"
    :items="icon_list"
    hide-actions
    class="elevation-1" 
    hide-headers="true"
  >
    <template slot="items" slot-scope="props">

      <td>
        <a :href="props.item.url" target="_blank">
          {{ props.item.name }}
        </a>
      </td>
      <td>{{ props.item.text }}</td>


      <td v-if="props.item.num == 1">
        <v-icon>fas fa-lock</v-icon>&nbsp;
        <v-icon>fas fa-tachometer-alt</v-icon>&nbsp;
        <v-icon>fas fa-search</v-icon>
      </td>
      <td v-else-if="props.item.num == 2">
        <v-icon>mdi-anchor</v-icon>&nbsp;
        <v-icon>mdi-tennis</v-icon>&nbsp;
        <v-icon>mdi-mouse</v-icon>
      </td>
      <td v-else-if="props.item.num == 3">
        <v-icon large color="green darken-2">business</v-icon>
        <v-icon large color="blue darken-2">chat</v-icon>
        <v-icon large color="purple darken-2">dialpad</v-icon>
      </td>
      <td v-else-if="props.item.num == 4">
        <v-btn color="red" dark>No<v-icon dark right>block</v-icon></v-btn>
        <v-btn flat icon color="red lighten-2"><v-icon>thumb_up</v-icon></v-btn>
      </td>
      <td v-else-if="props.item.num == 5">
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
        <v-badge left color="purple">
          <v-icon slot="badge" dark small>mdi-adjust</v-icon>
          <span>test1</span>
        </v-badge>&nbsp;&nbsp;
        <v-badge color="orange">
          <v-icon slot="badge" dark small>fas fa-fighter-jet</v-icon>
          <span>test2</span>
        </v-badge>
      </td>
      
    </template>
  </v-data-table>
</template>

<script>

  export default {
    data () {
      return {
        icon_list: [
          {
            value: false,
            name: 'Font Awesome',
            text: "Font AwesomeのWebアイコンフォント",
            url: "https://vuetifyjs.com/ja/components/icons#example-font-awesome",
            num: 1,
          },
          {
            value: false,
            name: 'Material Design Icons',
            text: "Material Design IconsのWebアイコンフォント",
            url: "https://vuetifyjs.com/ja/components/icons#example-mdi",
            num: 2,
          },
          {
            value: false,
            name: '色変更',
            text: "アイコンの色を変更する",
            url: "https://vuetifyjs.com/ja/components/icons#example-color",
            num: 3,
          },
          {
            value: false,
            name: 'アイコンとボタン',
            text: "ボタンとアイコンを融合する",
            url: "https://vuetifyjs.com/ja/components/icons#example-buttons",
            num: 4,
          },
          {
            value: false,
            name: 'アイコンのバッジ化',
            text: "アイコンをバッジとして使用する",
            url: "https://vuetifyjs.com/ja/components/badges#example-icon",
            num: 5,
          }, 
        ],
      }
    },
    methods: {
      next () {
        alert('You clicked next!')
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
