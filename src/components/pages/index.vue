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

          <v-expansion-panel-content>
            <div slot="header">ナビゲーション</div>
            <v-card>
              <v-card-text>
                <div>

                </div>
                <v-data-table
                  :headers="headers"
                  :items="nav_list"
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
            <div slot="header">パンくずリスト</div>
            <v-card>
              <v-card-text>
                <div>

                </div>
                <v-data-table
                  :headers="headers"
                  :items="breadcrumbs_list"
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
            <div slot="header">チップ</div>
            <v-card>
              <v-card-text>
                <div>
                  基本的な概要は「
                  <a href="https://vuetifyjs.com/ja/components/chips" target="_blank">v-chip</a>
                  」参照<br>
                  基本型、アイコン付、写真付、閉じるボタン付の4種類ある
                </div>
                <v-data-table
                  :headers="headers"
                  :items="chip_list"
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
            <div slot="header">ダイアログ</div>
            <v-card>
              <v-card-text>
                <div>
                  基本的な概要は「
                  <a href="https://vuetifyjs.com/ja/components/dialogs" target="_blank">v-dialog</a>
                  」参照<br>
                </div>
                <v-data-table
                  :headers="headers"
                  :items="dialog_list"
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
            <div slot="header">ジャンボトロン</div>
            <v-card>
              <v-card-text>
                <div>
                  基本的な概要は「
                  <a href="https://vuetifyjs.com/ja/components/jumbotrons" target="_blank">v-jumbotron</a>
                  」参照<br>
                </div>
                <v-data-table
                  :headers="headers"
                  :items="jumbotron_list"
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
            <div slot="header">リスト</div>
            <v-card>
              <v-card-text>
                <div>
                  基本的な概要は「
                  <a href="https://vuetifyjs.com/ja/components/lists" target="_blank">v-list</a>
                  」参照<br>
                </div>
                <v-data-table
                  :headers="headers"
                  :items="list_list"
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
            <div slot="header">ページネーション</div>
            <v-card>
              <v-card-text>
                <div>
                  基本的な概要は「
                  <a href="https://vuetifyjs.com/ja/components/paginations" target="_blank">v-pagination</a>
                  」参照<br>
                </div>
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
        ],
        nav_list: [
         {
            value: false,
            name: 'ボトムナビゲーションバー',
            text: "サイドバーの代わりとして使用可能。色の変更やシフトの切り替えもできる",
            url: "https://vuetifyjs.com/ja/components/bottom-navigation"
          }, 
          {
            value: false,
            name: 'ナビゲーションドロワー',
            text: "画面の左端に出るナビゲーション",
            url: "https://vuetifyjs.com/ja/components/navigation-drawers"
          }, 
        ],
        breadcrumbs_list: [
          {
            value: false,
            name: 'パンくずリスト',
            text: "アイコンの表示や、アイコンによる区切りなどができる",
            url: "https://vuetifyjs.com/ja/components/breadcrumbs"
          }, 
        ],
        chip_list: [
          {
            value: false,
            name: '色の設定',
            text: "チップに色をつける",
            url: "https://vuetifyjs.com/ja/components/chips#example-colored"
          },  
          {
            value: false,
            name: 'アイコンの設定',
            text: "チップにアイコンをつける",
            url: "https://vuetifyjs.com/ja/components/chips#example-icon"
          },
          {
            value: false,
            name: 'アウトラインチップ',
            text: "テキストの色を境界線として表示したチップ",
            url: "https://vuetifyjs.com/ja/components/chips#example-outline"
          },  
          {
            value: false,
            name: 'ラベル',
            text: "ラベルのチップ",
            url: "https://vuetifyjs.com/ja/components/chips#example-label"
          },
          {
            value: false,
            name: '閉じるボタン付きチップ',
            text: "チップに閉じるボタンをつける",
            url: "https://vuetifyjs.com/ja/components/chips#example-closable"
          }, 
          {
            value: false,
            name: 'セレクトとの組み合わせ',
            text: "選択された項目の表示にチップを使う",
            url: "https://vuetifyjs.com/ja/components/chips#example-in-selects"
          },   
        ],
        dialog_list: [
          {
            value: false,
            name: "◯",
            text: "",
            url: "https://vuetifyjs.com/ja/components/dialogs#example-without-activator"
          }, 
          {
            value: false,
            name: 'モーダル',
            text: "ダイアログ画面以外をクリックしても、閉じないようにする",
            url: "https://vuetifyjs.com/ja/components/dialogs#example-modal"
          }, 
          {
            value: false,
            name: 'フォーム',
            text: "ダイアログ画面にフォーム（form）を取り入れる",
            url: "https://vuetifyjs.com/ja/components/dialogs#example-form"
          },  
          {
            value: false,
            name: 'スクロール',
            text: "ダイアログ画面内でスクロールできるようにする",
            url: "https://vuetifyjs.com/ja/components/dialogs#example-scrollable"
          }, 
          {
            value: false,
            name: 'オーバーフロー',
            text: "ウィンドウ画面に収まらないダイアログ画面はスクロールする",
            url: "https://vuetifyjs.com/ja/components/dialogs#example-overflowed"
          }, 
          {
            value: false,
            name: '◯',
            text: "",
            url: "https://vuetifyjs.com/ja/components/dialogs#example-advanced"
          }, 
          {
            value: false,
            name: 'ローディング',
            text: "処理中であることをダイアログで表示する",
            url: "https://vuetifyjs.com/ja/components/dialogs#example-loader"
          },  
        ],
        jumbotron_list: [
          {
            value: false,
            name: '背景色の変更',
            text: "背景色を変更する",
            url: "https://vuetifyjs.com/ja/components/jumbotrons#example-color"
          },
          {
            value: false,
            name: '色のグラデーション',
            text: "グラデーションカラーを設定する",
            url: "https://vuetifyjs.com/ja/components/jumbotrons#example-gradient"
          },
          {
            value: false,
            name: '画像のグラデーション',
            text: "画像をグラデーションに設定する",
            url: "https://vuetifyjs.com/ja/components/jumbotrons#example-gradient-with-image"
          },  
        ],
        list_list: [
          {
            value: false,
            name: '区切り線',
            text: "リスト間を区切る線。テーマ変更、インデント設定も可能",
            url: "https://vuetifyjs.com/ja/components/dividers"
          },  
          {
            value: false,
            name: '◯',
            text: "",
            url: "https://vuetifyjs.com/ja/components/lists#example-avatar-title-and-action"
          }, 
          {
            value: false,
            name: '2行表示',
            text: "",
            url: "https://vuetifyjs.com/ja/components/lists#example-icon-two-lines-and-action"
          },
          {
            value: false,
            name: '3行表示',
            text: "",
            url: "https://vuetifyjs.com/ja/components/lists#example-avatar-three-lines"
          },          
          {
            value: false,
            name: 'Avatar with title and action',
            text: "",
            url: "https://vuetifyjs.com/ja/components/lists#example-avatar-subheader-title-and-action"
          }, 
          {
            value: false,
            name: 'Subheadings and dividers',
            text: "",
            url: "https://vuetifyjs.com/ja/components/lists#example-subheadings-and-dividers"
          },  
          {
            value: false,
            name: 'カード入りリスト',
            text: "カード（v-card）を含んだリスト",
            url: "https://vuetifyjs.com/ja/components/lists#example-card-list"
          },  
          {
            value: false,
            name: 'Title with sub-title, actions and action-text',
            text: "",
            url: "https://vuetifyjs.com/ja/components/lists#example-title-subtitle-actions-and-action-text"
          },  
          {
            value: false,
            name: 'Action with title and sub-title',
            text: "",
            url: "https://vuetifyjs.com/ja/components/lists#example-action-title-and-subtitle"
          },  
          {
            value: false,
            name: '拡張リスト',
            text: "拡張機能を含んだリスト",
            url: "https://vuetifyjs.com/ja/components/lists#example-expansion-lists"
          },  
        ],
        pagination_list:[
          {
            value: false,
            name: '拡張リスト',
            text: "拡張機能を含んだリスト",
            url: "https://vuetifyjs.com/ja/components/lists#example-expansion-lists"
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