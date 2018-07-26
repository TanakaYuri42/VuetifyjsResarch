<template>
  <v-data-table
    :headers="headers"
    :items="badge_list"
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


      <td v-if="props.item.num == 1" colspan="2">
        <v-badge
          color="purple"
          left
          overlap
          style="margin-top:10px;"
        >
          <v-icon
            slot="badge"
            dark
            small
          >done</v-icon>
          <v-icon
            color="grey lighten-1"
            large
          >
            account_circle
          </v-icon>
        </v-badge>
        <v-badge
          overlap
          color="orange"
        >
          <v-icon
            slot="badge"
            dark
            small
          >notifications</v-icon>
          <v-icon
            large
            color="grey darken-1"
          >
            account_box
          </v-icon>
        </v-badge>
      </td>

      <td v-else-if="props.item.num == 2" colspan="2">
        &nbsp;&nbsp;&nbsp;
        <v-badge left>
          <span slot="badge">2</span>
          <span>Inline</span>
        </v-badge>
        &nbsp;&nbsp;
        <v-badge color="green">
          <v-icon slot="badge" dark small>list</v-icon>
          <span>Budge</span>
        </v-badge>
      </td>
      
      <td v-else-if="props.item.num == 3" colspan="2">
        &nbsp;&nbsp;&nbsp;
        <v-badge left color="purple">
          <v-icon slot="badge" dark small>mdi-adjust</v-icon>
          <span>Icon</span>
        </v-badge>
        &nbsp;&nbsp;&nbsp;&nbsp;
        <v-badge color="orange">
          <v-icon slot="badge" dark small>fas fa-fighter-jet</v-icon>
          <span>Budge</span>
        </v-badge>
      </td>

      <td v-else-if="props.item.num == 4" colspan="2">
        <v-btn
          color="indigo"
          class="white--text"
          @click="show = !show"
          style="margin-top:-30px;"
        >
          Click
        </v-btn>
        <v-badge
          v-model="show"
          color="cyan"
          style="margin-top:15px;"
        >
          <span slot="badge">6</span>
          <v-icon
            large
            color="grey lighten-1"
          >shopping_cart</v-icon>
        </v-badge>
      </td>
    
    </template>
  </v-data-table>
</template>

<script>

  export default {
    data () {
      return {
        badge_list: [
          {
            value: false,
            name: '重ね合わせ',
            text: "バッジを要素と重なるように配置する",
            url: "https://vuetifyjs.com/ja/components/badges#example-overlap",
            num: 1,
          },  
          {
            value: false,
            name: 'インライン',
            text: "バッジをテキスト内に配置する",
            url: "https://vuetifyjs.com/ja/components/badges#example-inline",
            num: 2,
          },  
          {
            value: false,
            name: 'アイコンのバッジ化',
            text: "アイコンをバッジとして使用する",
            url: "https://vuetifyjs.com/ja/components/badges#example-icon",
            num: 3,
          },
          {
            value: false,
            name: 'バッジの表示切り替え',
            text: "バッジの表示・非表示を切り替える",
            url: "https://vuetifyjs.com/ja/components/badges#example-visibility",
            num: 4,
          }, 
        ],
        show: true,
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
