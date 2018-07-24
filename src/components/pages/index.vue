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
            <div slot="header">ボタン</div>
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
                      <td>
                        <a :href="props.item.url" target="_blank">
                          {{ props.item.name }}
                        </a>
                      </td>
                    <td>{{ props.item.text }}</td>
                  </template>
                </v-data-table>
              </v-card-text>
            </v-card>
          </v-expansion-panel-content>

          <v-expansion-panel-content>
            <div slot="header">アイコン</div>
            <v-card>
              <v-card-text>
                <div>
                  基本的な概要は「
                  <a href="https://vuetifyjs.com/ja/components/icons" target="_blank">v-icon</a>
                  」参照<br>
                  テーマ（light,dark）と、サイズ（standard、medium、large、x-large）の設定が可能
                </div>
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
                  </template>
                </v-data-table>
              </v-card-text>
            </v-card>
          </v-expansion-panel-content>

          <v-expansion-panel-content>
            <div slot="header">アラート</div>
            <v-card>
              <v-card-text>
                <div>
                  基本的な概要は「
                  <a href="https://vuetifyjs.com/ja/components/alerts" target="_blank">v-alert</a>
                  」参照<br>
                  4つのバリエーション（success、info、warning、error）の設定が可能
                </div>
                <v-data-table
                  :headers="headers"
                  :items="alert_list"
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
                  </template>
                </v-data-table>
              </v-card-text>
            </v-card>
          </v-expansion-panel-content>

          <v-expansion-panel-content>
            <div slot="header">バッジ</div>
            <v-card>
              <v-card-text>
                <div>
                  基本的な概要は「
                  <a href="https://vuetifyjs.com/ja/components/badges" target="_blank">v-badge</a>
                  」参照<br>
                </div>
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
            url: "https://vuetifyjs.com/ja/components/buttons#example-flat",
          },
          {
            value: false,
            name: 'レイズドボタン',
            text: "クリックした時に影が広がるボタン",
            url:"https://vuetifyjs.com/ja/components/buttons#example-raised",
          },
          {
            value: false,
            name: 'ディプレスドボタン',
            text: "背景色は持つが、影は持たないボタン",
            url: "https://vuetifyjs.com/ja/components/buttons#example-depressed",
          },
          {
            value: false,
            name: 'ドロップダウンボタン',
            text: "クリックするとリストを表示できるボタン",
            url: "https://vuetifyjs.com/ja/components/buttons#example-depressed",
          },
          {
            value: false,
            name: 'トグルボタン',
            text: "ラジオボタンやチェックボックスの作成",
            url:"https://vuetifyjs.com/ja/components/buttons#example-toggle"
          },
          {
            value: false,
            name: 'アイコンボタン',
            text: "アイコンをボタンとして使用する",
            url: "https://vuetifyjs.com/ja/components/buttons#example-icon",
          },
          {
            value: false,
            name: 'フローティングボタン',
            text: "丸いボタン",
            url: "https://vuetifyjs.com/ja/components/buttons#example-floating"
          },
          {
            value: false,
            name: 'ローディング',
            text: "クリックすると、処理中であることを表示するボタン",
            url: "https://vuetifyjs.com/ja/components/buttons#example-loaders"
          },
          {
            value: false,
            name: 'サイズ変更',
            text: "smallやlargeなど、ボタンのサイズを変更する",
            url: "https://vuetifyjs.com/ja/components/buttons#example-sizing"
          },
          {
            value: false,
            name: 'アウトラインボタン',
            text: "現在適用されている色を境界線として表示したボタン",
            url: "https://vuetifyjs.com/ja/components/buttons#example-outline"
          },
          {
            value: false,
            name: 'ラウンドボタン',
            text: "角が丸くなったボタン",
            url: "https://vuetifyjs.com/ja/components/buttons#example-round"
          },
          {
            value: false,
            name: 'ブロック',
            text: "可能な限り横に広がったボタン",
            url: "https://vuetifyjs.com/ja/components/buttons#example-block"
          },
          {
            value: false,
            name: 'ツールバー',
            text: "ツールバーとボタンを融合させる",
            url: "https://vuetifyjs.com/ja/components/buttons#example-app-bar"
          },
        ],
        icon_list: [
          {
            value: false,
            name: 'Font Awesome',
            text: "Font AwesomeのWebアイコンフォント",
            url: "https://vuetifyjs.com/ja/components/icons#example-font-awesome"
          },
          {
            value: false,
            name: 'Material Design Icons',
            text: "Material Design IconsのWebアイコンフォント",
            url: "https://vuetifyjs.com/ja/components/icons#example-mdi"
          },
          {
            value: false,
            name: '色変更',
            text: "アイコンの色を変更する",
            url: "https://vuetifyjs.com/ja/components/icons#example-color"
          },
          {
            value: false,
            name: 'アイコンボタン',
            text: "ボタンとアイコンの融合や、アイコンをボタンとしての使用",
            url: "https://vuetifyjs.com/ja/components/icons#example-buttons"
          },
          {
            value: false,
            name: 'アイコンバッジ',
            text: "アイコンをバッジとして使用する",
            url: "https://vuetifyjs.com/ja/components/badges#example-icon"
          }, 
          {
            value: false,
            name: 'クリックイベント時のカーソル変更',
            text: "クリックイベントをv-iconと結ぶことで、自動的にカーソルをポインタに変更する",
            url: "https://vuetifyjs.com/ja/components/icons#example-clickable"
          },
        ],
        alert_list: [
          {
            value: false,
            name: '閉じるボタン付きアラート',
            text: "アラートに閉じるボタンをつける",
            url: "https://vuetifyjs.com/ja/components/alerts#example-closable"
          },
          {
            value: false,
            name: 'アイコンの設定変更',
            text: "アラートのアイコンの変更や削除",
            url: "https://vuetifyjs.com/ja/components/alerts#example-icon"
          },
          {
            value: false,
            name: 'トランジション設定',
            text: "アラート表示・非表示の際に、トランジションを設定する",
            url: "https://vuetifyjs.com/ja/components/alerts#example-transition"
          },
          {
            value: false,
            name: 'アウトラインアラート',
            text: "現在適用されている色を境界線として表示したアラート",
            url: "https://vuetifyjs.com/ja/components/alerts#example-outline"
          },
        ],
        badge_list: [
          {
            value: false,
            name: '重ね合わせ',
            text: "バッジを要素と重なるように配置する",
            url: "https://vuetifyjs.com/ja/components/badges#example-overlap"
          },  
          {
            value: false,
            name: 'インライン',
            text: "バッジをテキスト内に配置する",
            url: "https://vuetifyjs.com/ja/components/badges#example-inline"
          },  
          {
            value: false,
            name: 'アイコンバッジ',
            text: "アイコンをバッジとして使用する",
            url: "https://vuetifyjs.com/ja/components/badges#example-icon"
          },
          {
            value: false,
            name: 'バッジの表示切り替え',
            text: "バッジを表示したり、非表示にしたりする",
            url: "https://vuetifyjs.com/ja/components/badges#example-visibility"
          }, 
        ]
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