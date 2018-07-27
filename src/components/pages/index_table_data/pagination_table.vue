<template>
  <v-data-table
    :headers="headers"
    :items="pagination_list"
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
          <div class="text-xs-center">
              <v-pagination
                v-model="page1"
                :length="15"
                :total-visible="5"
              ></v-pagination>
            </div>
        </td>


        <td v-else-if="props.item.num == 2" colspan="2">
          <div class="text-xs-center">
            <v-pagination
              v-model="page2"
              :length="5"
              circle
            ></v-pagination>
          </div>    
        </td>

        <td v-else-if="props.item.num == 3" colspan="2">
          <div class="text-xs-center">
            <v-pagination
              v-model="page3"
              :length="5"
              prev-icon="mdi-menu-left"
              next-icon="mdi-menu-right"
            ></v-pagination>
          </div>
        </td>

        <td v-else-if="props.item.num == 4" colspan="2">
          <div class="text-xs-center">
            <v-pagination
              :length="5"
              disabled
            ></v-pagination>
          </div>
        </td>
    
    </template>
  </v-data-table>
</template>

<script>

  export default {
    data () {
      return {
        pagination_list:[
          {
            value: false,
            name: '最大ページ数の設定',
            text: "表示可能な最大ページ数を手動で設定する",
            url: "https://vuetifyjs.com/ja/components/paginations#example-limit",
            num: 1,
          }, 
          {
            value: false,
            name: 'ラウンド',
            text: "ページ数を囲む線の角を丸くする",
            url: "https://vuetifyjs.com/ja/components/paginations#example-round",
            num: 2,
          },  
          {
            value: false,
            name: 'アイコン',
            text: "ページ移動のボタンをアイコンにする",
            url: "https://vuetifyjs.com/ja/components/paginations#example-icons",
            num: 3,
          },  
          {
            value: false,
            name: 'ページ移動無効化',
            text: "ページ移動をできないようにする",
            url: "https://vuetifyjs.com/ja/components/paginations#example-disabled",
            num: 4
          },  
        ],
        page1: 1,
        page2: 1,
        page3: 1,
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

table{
  border:solid 1px #ddd;
  width:100%;
}

td{
  border:solid 1px #ddd;
}
</style>
