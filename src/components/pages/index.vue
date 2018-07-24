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

          <v-expansion-panel-content>
            <div slot="header">ピッカー</div>
            <v-card>
              <v-card-text>
                <div>
                  ユーザーが視覚的に選択できるようにする。ここではDate pickerとTime pickerを紹介する
                </div>
                <v-data-table
                  :headers="headers"
                  :items="picker_list"
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
            <div slot="header">プログレスバー（丸）</div>
            <v-card>
              <v-card-text>
                <div>
                  基本的な概要は「
                  <a href="https://vuetifyjs.com/ja/components/progress" target="_blank">
                    v-progress-circular
                  </a>
                  」参照<br>
                </div>
                <v-data-table
                  :headers="headers"
                  :items="progresscircle_list"
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
            <div slot="header">プログレスバー（棒線）</div>
            <v-card>
              <v-card-text>
                <div>
                  基本的な概要は「
                  <a href="https://vuetifyjs.com/ja/components/progress" target="_blank">
                    v-progress-liner
                  </a>
                  」参照<br>
                </div>
                <v-data-table
                  :headers="headers"
                  :items="progressliner_list"
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
            <div slot="header">タブ</div>
            <v-card>
              <v-card-text>
                <div>
                  基本的な概要は「
                  <a href="https://vuetifyjs.com/ja/components/tabs" target="_blank">
                    v-tabs
                  </a>
                  」参照<br>
                </div>
                <v-data-table
                  :headers="headers"
                  :items="tab_list"
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
            <div slot="header">ツールバー</div>
            <v-card>
              <v-card-text>
                <div>
                  基本的な概要は「
                  <a href="https://vuetifyjs.com/ja/components/toolbars" target="_blank">
                    v-toolbar
                  </a>
                  」参照<br>
                </div>
                <v-data-table
                  :headers="headers"
                  :items="toolbar_list"
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
          {
            value: false,
            name: 'ツールチップ',
            text: "要素にホバーやクリックすることでチップを表示する",
            url: "https://vuetifyjs.com/ja/components/tooltips"
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
            name: 'ページ数が多い時のリスト切り捨て',
            text: "ページ数が親コンテンツを超えた場合、リストを切り捨てる",
            url: "https://vuetifyjs.com/ja/components/paginations#example-limit"
          }, 
          {
            value: false,
            name: 'ラウンド',
            text: "ページ数を囲む線の角を丸くする",
            url: "https://vuetifyjs.com/ja/components/paginations#example-round"
          },  
          {
            value: false,
            name: 'アイコン',
            text: "ページ移動のボタンをアイコンにする",
            url: "https://vuetifyjs.com/ja/components/paginations#example-icons"
          },  
          {
            value: false,
            name: 'ページ移動無効',
            text: "ページ移動をできないようにする",
            url: "https://vuetifyjs.com/ja/components/paginations#example-disabled"
          },  
        ],
        picker_list: [
          {
            value: false,
            name: 'Date picker（カレンダー）',
            text: "日付/月を選択するためのカレンダーを表示する",
            url: "https://vuetifyjs.com/ja/components/date-pickers"
          },  
          {
            value: false,
            name: 'Time picker（時計）',
            text: "時間を選択するための時計を表示する",
            url: "https://vuetifyjs.com/ja/components/time-pickers"
          },  
        ],
        progresscircle_list:[
          {
            value: false,
            name: '色の設定',
            text: "プログレスバーに色をつける",
            url: "https://vuetifyjs.com/ja/components/progress#example-circular-colored"
          },  
          {
            value: false,
            name: '不確定',
            text: "進行の割合を不確定なプログレスバー。延々とアニメーションする",
            url: "https://vuetifyjs.com/ja/components/progress#example-circular-indeterminate"
          }, 
          {
            value: false,
            name: 'サイズ変更',
            text: "プログレスバーのサイズを変更する",
            url: "https://vuetifyjs.com/ja/components/progress#example-circular-size-and-width"
          },  
          {
            value: false,
            name: '回転',
            text: "プログレスバーを進行に合わせて回転させる",
            url: "https://vuetifyjs.com/ja/components/progress#example-circular-rotate"
          },  
        ],
        progressliner_list: [
          {
            value: false,
            name: '確定',
            text: "進行の割合が確定しているプログレスバー",
            url: "https://vuetifyjs.com/ja/components/progress#example-linear-determinate"
          },  
          {
            value: false,
            name: '確定',
            text: "進行の割合が不確定なプログレスバー。延々とアニメーションする",
            url: "https://vuetifyjs.com/ja/components/progress#example-linear-indeterminate"
          },  
          {
            value: false,
            name: 'バッファ',
            text: "",
            url: "https://vuetifyjs.com/ja/components/progress#example-linear-buffer"
          },
          {
            value: false,
            name: '高さ・色の設定',
            text: "プログレスバーの高さや色を設定する",
            url: "https://vuetifyjs.com/ja/components/progress#example-linear-custom-height-and-contextual-colors"
          },  
          {
            value: false,
            name: '進行バーの色・背景色の設定',
            text: "プログレスバーの進行中のバーの色と背景色を設定する",
            url: "https://vuetifyjs.com/ja/components/progress#example-linear-custom-colors"
          },  
        ],
        tab_list: [
          {
            value: false,
            name: '固定タブ',
            text: "より大きい最小幅を設定して適当したタブ",
            url: "https://vuetifyjs.com/ja/components/tabs#example-fixed-tabs"
          },  
          {
            value: false,
            name: '右揃え',
            text: "右揃えに並べたタブ",
            url: "https://vuetifyjs.com/ja/components/tabs#example-right"
          },  
          {
            value: false,
            name: 'コンテンツ',
            text: "タブ内にツールバーなど、他のコンテンツも取り入れる",
            url: "https://vuetifyjs.com/ja/components/tabs#example-content"
          },  
          {
            value: false,
            name: '検索機能',
            text: "タブ内に検索機能を取り入れる",
            url: "https://vuetifyjs.com/ja/components/tabs#example-search"
          },  
          {
            value: false,
            name: 'アイコンとテキスト',
            text: "タブをアイコンとテキストで表示する",
            url: "https://vuetifyjs.com/ja/components/tabs#example-icons-and-text"
          },  
          {
            value: false,
            name: 'タブとツールバーの整列',
            text: "タブをツールバーのタイトルと並べる",
            url: "https://vuetifyjs.com/ja/components/tabs#example-align-with-title"
          },  
          {
            value: false,
            name: '最大幅での表示',
            text: "利用可能な領域を全て使ってタブを表示する",
            url: "https://vuetifyjs.com/ja/components/tabs#example-grow"
          },  
          {
            value: false,
            name: 'メニュー付き',
            text: "タブの中にメニューをつけて、追加のタブを表示する",
            url: "https://vuetifyjs.com/ja/components/tabs#example-overflow-to-menu"
          }, 
          {
            value: false,
            name: 'ページネーション',
            text: "タブ数が親コンテンツを越えた時、ページネーション表示にする",
            url: "https://vuetifyjs.com/ja/components/tabs#example-pagination"
          },  
          {
            value: false,
            name: 'ページネーションにアイコン付加',
            text: "ページネーションのページ移動のボタンをアイコンにする",
            url: "https://vuetifyjs.com/ja/components/tabs#example-icons"
          },  
        ],
        toolbar_list: [
          {
            value: false,
            name: 'アプリケーションバー',
            text: "アプリケーションの主要なツールバー。アイコンやメニューの追加可能",
            url: "https://vuetifyjs.com/ja/components/toolbars#example-app-bar"
          },  
          {
            value: false,
            name: 'ボタンを使用したアプリケーションバー',
            text: "ボタンをアプリケーション項目として作成する",
            url: "https://vuetifyjs.com/ja/components/toolbars#example-app-bar-items"
          },  
          {
            value: false,
            name: '拡張機能付き',
            text: "拡張機能を追加したアプリケーションバー",
            url: "https://vuetifyjs.com/ja/components/toolbars#example-app-bar-extension"
          },  
          {
            value: false,
            name: '幅を階層化する',
            text: "ツールバーの幅を階層化する",
            url: "https://vuetifyjs.com/ja/components/toolbars#example-column-width-with-hierarchy"
          },
          {
            value: false,
            name: '柔軟なツールバー',
            text: "カード（v-card）を含めるなど、ツールバーを柔軟にカスタムする",
            url: "https://vuetifyjs.com/ja/components/toolbars#example-flexible-and-card"
          },  
          {
            value: false,
            name: '検索付きフローティングツールバー',
            text: "検索機能をつけて、参照するコンテンツ上にツールバーを設置する",
            url: "https://vuetifyjs.com/ja/components/toolbars#example-floating-with-search"
          },  
          {
            value: false,
            name: 'バリエーション',
            text: "テーマやヘルパークラスなど、バリエーションを設定する",
            url: "https://vuetifyjs.com/ja/components/toolbars#example-variations"
          },  
          {
            value: false,
            name: '顕著なツールバー',
            text: "拡張領域に、要素を配置できるスロットを追加する",
            url: "https://vuetifyjs.com/ja/components/toolbars#example-prominent"
          },  
          {
            value: false,
            name: '密なツールバー',
            text: "高さを48pxに減らす",
            url: "https://vuetifyjs.com/ja/components/toolbars#example-dense"
          },  
          {
            value: false,
            name: 'スクロール',
            text: "スクロールする時に、ツールバーを画面から切り替える",
            url: "https://vuetifyjs.com/ja/components/toolbars#example-scrolling"
          },  
          {
            value: false,
            name: 'メニュー付きアプリケーションバー',
            text: "アプリケーションバーにメニューをつける",
            url: "https://vuetifyjs.com/ja/components/toolbars#example-app-bar-menu"
          }, 
          {
            value: false,
            name: 'システムバー',
            text: "システムバーを作成する",
            url: "https://vuetifyjs.com/ja/components/toolbars#example-system-bars-status-window"
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