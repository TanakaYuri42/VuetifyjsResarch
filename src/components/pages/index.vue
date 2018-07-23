<template>
      <div>
        <div class="d-flex justify-between align-center mb-3">
          <!-- <v-btn @click="all">all</v-btn>
          <v-btn @click="none">none</v-btn> -->
        </div>

        <v-expansion-panel
          v-model="panel"
          expand
        >
          <v-expansion-panel-content>
            <div slot="header">ボタン機能</div>
            <v-card>
              <v-card-text>
                <div>
                  基本的な概要は「
                  <a href="https://vuetifyjs.com/ja/components/buttons" target="_blank">v-btn</a>
                  」参照
                </div>
                <v-data-table
                  :headers="headers"
                  :items="button_list"
                  hide-actions
                  class="elevation-1" 
                  hide-headers="true"
                >
                  <template slot="items" slot-scope="props">
                      <td :to="props.item.url" >
                          {{ props.item.name }}
                      </td>
                    <td>{{ props.item.text }}</td>
                  </template>
                </v-data-table>
              </v-card-text>
            </v-card>
          </v-expansion-panel-content>


        </v-expansion-panel>

      </div>
</template>

<script>
  export default {
    data () {
      return {
      button_list: [
          {
            value: false,
            name: "フラットボタン",
            text: "影と背景色を持たないボタン。カーソルを合わせると背景が浮かび上がる",
            url: "https://vuetifyjs.com/ja/components/buttons#examples",
          },
          {
            value: false,
            name: 'レイズドボタン',
            text: "クリックした時に影が広がるボタン"
          },
          {
            value: false,
            name: 'ディプレスドボタン',
            text: "背景色は持つが、影は持たないボタン"
          },
          {
            value: false,
            name: 'ドロップダウンボタン',
            text: "クリックするとリストを表示できるボタン"
          },
          {
            value: false,
            name: 'トグルボタン',
            text: "ラジオボタンやチェックボックスのこと"
          },
          {
            value: false,
            name: 'アイコンボタン',
            text: "アイコンをボタンとして使用したもの"
          },
          {
            value: false,
            name: 'フローティングボタン',
            text: "丸いボタン"
          },
          {
            value: false,
            name: 'ローディング',
            text: "クリックすると、処理中であることを表示するボタン"
          },
          {
            value: false,
            name: 'サイズ変更',
            text: "smallやlargeなど、ボタンのサイズを変更する"
          },
          {
            value: false,
            name: 'アウトラインボタン',
            text: "現在適用されている色を境界線として表示したボタン"
          },
          {
            value: false,
            name: 'ラウンドボタン',
            text: "角が丸くなったボタン"
          },
          {
            value: false,
            name: 'ブロック',
            text: "可能な限り横に広がったボタン"
          },
          {
            value: false,
            name: 'ツールバー',
            text: "ツールバーとボタンを融合させる"
          },
        ],
      }
    },
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