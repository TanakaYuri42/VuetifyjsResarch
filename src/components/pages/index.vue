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
                  <ButtonTable/>
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
                <Icon/>
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
                <Alert/>
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
                <Badge/>
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
                <Chip/>
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
            <div slot="header">テーブル</div>
            <v-card>
              <v-card-text>
                <div>
                  基本的な概要は「
                  <a href="https://vuetifyjs.com/ja/components/data-tables" target="_blank">
                    v-data-table
                  </a>
                  」参照<br>
                  表形式でデータ表示。ソート、検索、ページネーション、編集、行選択などの機能を含んでいる
                </div>
                <v-data-table
                  :headers="headers"
                  :items="table_list"
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
            <div slot="header">イテレータ</div>
            <v-card>
              <v-card-text>
                <div>
                  基本的な概要は「
                  <a href="https://vuetifyjs.com/ja/components/data-iterator" target="_blank">
                    v-data-iterator
                  </a>
                  」参照<br>
                  データ表示を細かくカスタマイズする。テーブルと似ている
                </div>
              </v-card-text>
            </v-card>
          </v-expansion-panel-content>

          <v-expansion-panel-content>
            <div slot="header">カード</div>
            <v-card>
              <v-card-text>
                <div>
                  基本的な概要は「
                  <a href="https://vuetifyjs.com/ja/components/cards" target="_blank">
                    v-card
                  </a>
                  」参照<br>
                  パネルや画像表示など、あらゆる用途に使用できる汎用的なコンポーネント<br>
                </div>
                <v-data-table
                  :headers="headers"
                  :items="card_list"
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
                <div style="padding-bottom:20px;">
                  基本的な概要は「
                  <a href="https://vuetifyjs.com/en/components/breadcrumbs" target="_blank">v-breadcrumbs</a>
                  」参照<br>
                  アイコン表示や、アイコンによる区切りも設定できる
                </div>
                <v-divider></v-divider>
                <div class="text-xs-center d-flex align-center">
                  <v-breadcrumbs divider="/" style="display:inline;">
                    <v-breadcrumbs-item
                      v-for="item in items"
                      :key="item.text"
                      :disabled="item.disabled"
                    >
                      {{ item.text }}
                    </v-breadcrumbs-item>
                  </v-breadcrumbs>
                  <v-breadcrumbs style="display:inline;">
                    <v-icon slot="divider">forward</v-icon>
                    <v-breadcrumbs-item
                      v-for="item in items"
                      :disabled="item.disabled"
                      :key="item.text"
                    >
                      {{ item.text }}
                    </v-breadcrumbs-item>
                  </v-breadcrumbs>
                </div>
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
                  シンプルなダイアログの見本は<a href="https://vuetifyjs.com/ja/components/dialogs#example-advanced" target="_blank">こちら</a>
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
            <div slot="header">フッター</div>
            <v-card>
              <v-card-text>
                <div>
                  基本的な概要は「
                  <a href="https://vuetifyjs.com/ja/components/footer" target="_blank">
                    v-footer
                  </a>
                  」参照
                </div>
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
                <ProgressC/>
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
                <Progress-l/>
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
            <div slot="header">拡張パネル</div>
            <v-card>
              <v-card-text>
                <div>
                  基本的な概要は「
                  <a href="https://vuetifyjs.com/ja/components/expansion-panels" target="_blank">
                    v-expansion-panel
                  </a>
                  」参照<br>
                </div>
                <v-data-table
                  :headers="headers"
                  :items="panel_list"
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
            <div slot="header">アバター</div>
            <v-card>
              <v-card-text>
                <div>
                  基本的な概要は「
                  <a href="https://vuetifyjs.com/ja/components/avatars" target="_blank">
                    v-avatar
                  </a>
                  」参照<br>
                  ユーザーの操作に合わせて、動的に要素のサイズ変更や角丸処理を行う
                </div>
              </v-card-text>
            </v-card>
          </v-expansion-panel-content>

          <v-expansion-panel-content>
            <div slot="header">スナックバー</div>
            <v-card>
              <v-card-text>
                <div>
                  基本的な概要は「
                  <a href="https://vuetifyjs.com/ja/components/snackbars" target="_blank">
                    v-snackbar
                  </a>
                  」参照<br>
                  ユーザーに対して、短いメッセージを表示する。実装に合わせて色の変更も可能
                </div>
              </v-card-text>
            </v-card>
          </v-expansion-panel-content>
        
          <v-expansion-panel-content>
            <div slot="header">パララックス</div>
            <v-card>
              <v-card-text>
                <div>
                  基本的な概要は「
                  <a href="https://vuetifyjs.com/ja/components/parallax" target="_blank">
                    v-parallax
                  </a>
                  」参照<br>
                  画像をウィンドウよりも遅くスクロールすることで3Dエフェクトを作成する
                </div>
              </v-card-text>
            </v-card>
          </v-expansion-panel-content>

          <v-expansion-panel-content>
            <div slot="header">ボトムシート</div>
            <v-card>
              <v-card-text>
                <div>
                  基本的な概要は「
                  <a href="https://vuetifyjs.com/ja/components/bottom-sheets" target="_blank">
                    v-bottom-sheet
                  </a>
                  」参照<br>
                  スクリーンの下部からスライドするように表示されるシート
                </div>
              </v-card-text>
            </v-card>
          </v-expansion-panel-content>

          <v-expansion-panel-content>
            <div slot="header">カルーセル</div>
            <v-card>
              <v-card-text>
                <div>
                  基本的な概要は「
                  <a href="https://vuetifyjs.com/ja/components/carousels" target="_blank">
                    v-carousel
                  </a>
                  」参照<br>
                  時間経過や操作によって画像が入れ替わる、大画面のビジュアルコンテンツ
                </div>
              </v-card-text>
            </v-card>
          </v-expansion-panel-content>

          <v-expansion-panel-content>
            <div slot="header">ステッパー</div>
            <v-card>
              <v-card-text>
                <div>
                  基本的な概要は「
                  <a href="https://vuetifyjs.com/ja/components/steppers" target="_blank">
                    v-stepper
                  </a>
                  」参照<br>
                  ユーザーが番号付きのステップを経て、操作を進行するための画面
                </div>
                <v-data-table
                  :headers="headers"
                  :items="stepper_list"
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
import ButtonTable from './index_table_data/button_table'
import Icon from './index_table_data/icon_table'
import Alert from './index_table_data/alert_table'
import Badge from './index_table_data/badge_table'
import Chip from './index_table_data/chip_table'
import ProgressC from './index_table_data/progress_c_table'
import ProgressL from './index_table_data/progress_l_table'

  export default {
    components: {
      ButtonTable,
      Icon,
      Alert,
      Badge,
      Chip,
      ProgressC,
      ProgressL
    },
    data () {
      return {
        items: [
          {text: 'Dashboard', disabled: false},
          {text: 'Link 1',disabled: false},
          {text: 'Link 2',disabled: true}
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
          {
            value: false,
            name: 'ツールバー',
            text: "主に画面の上に出てくるバー",
            url: "https://vuetifyjs.com/ja/components/toolbars"
          }, 
          {
            value: false,
            name: 'メニュー',
            text: "ほぼ全ての要素に配置可能",
            url: "https://vuetifyjs.com/ja/components/menus"
          }, 
          {
            value: false,
            name: 'リスト',
            text: "リンクオプション有り。上記のナビゲーション等と組み合わせやすい",
            url: "https://vuetifyjs.com/ja/components/lists"
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
        dialog_list: [
          {
            value: false,
            name: 'モーダル',
            text: "ダイアログ画面外をクリックしても、閉じないようにする",
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
            name: 'カード入りリスト',
            text: "カード（v-card）を含んだリスト",
            url: "https://vuetifyjs.com/ja/components/lists#example-card-list"
          }, 
          {
            value: false,
            name: '拡張リスト',
            text: "拡張機能を含んだリスト",
            url: "https://vuetifyjs.com/ja/components/lists#example-expansion-lists"
          },  
          {
            value: false,
            name: 'サブヘッダー',
            text: "リストのセクションを区切るために使用されるもの",
            url: "https://vuetifyjs.com/ja/components/subheaders"
          },  
        ],
        pagination_list:[
          {
            value: false,
            name: 'ページ数が多い時のリスト切り捨て',
            text: "ページ数が親コンテンツを超えた場合、ページ数の表示を切り捨てる",
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
            name: 'ページ移動無効化',
            text: "ページ移動をできないようにする",
            url: "https://vuetifyjs.com/ja/components/paginations#example-disabled"
          },  
        ],
        picker_list: [
          {
            value: false,
            name: 'Date/month picker（カレンダー）',
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
        tab_list: [
          {
            value: false,
            name: '固定タブ',
            text: "より大きい最小幅を設定して適応したタブ",
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
            text: "タブ内に他コンテンツ（ツールバーなど）を取り入れる",
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
            text: "ボタンをアプリケーション項目として追加する",
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
            name: '主要なツールバー',
            text: "拡張領域に、要素を配置できるスロットを追加する",
            url: "https://vuetifyjs.com/ja/components/toolbars#example-prominent"
          },  
          {
            value: false,
            name: '高密度のツールバー',
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
        ],
        panel_list: [
          {
            value: false,
            name: '展開パネル',
            text: "閉じるまでは開いたままのパネル",
            url: "https://vuetifyjs.com/ja/components/expansion-panels#example-expand"
          }, 
          {
            value: false,
            name: '外部コントロール',
            text: "パネル外から操作することでパネルを開閉する",
            url: "https://vuetifyjs.com/ja/components/expansion-panels#example-external"
          }, 
          {
            value: false,
            name: '無効、読み取り専用',
            text: "開閉無効のパネル及び、読み取り専用のパネル",
            url: "https://vuetifyjs.com/ja/components/expansion-panels#example-disabled-and-readonly"
          }, 
          {
            value: false,
            name: 'ポップアウトとインセット',
            text: "パネルが外に飛び出すように開いたり、中に引っ込むように開いたりする",
            url: "https://vuetifyjs.com/ja/components/expansion-panels#example-popout"
          }, 
          {
            value: false,
            name: 'フォーカス',
            text: "パネルを開いた際に、目立つようフォーカスする",
            url: "https://vuetifyjs.com/ja/components/expansion-panels#example-focusable"
          }, 
        ],
        table_list: [
          {
            value: false,
            name: 'データがない時の設定',
            text: "データが存在しない時に表示するhtmlを設定する",
            url: "https://vuetifyjs.com/ja/components/data-tables#example-no-data"
          }, 
          {
            value: false,
            name: 'ヘッダーのセルごとの共通設定',
            text: "ヘッダーのセルごとに共通のマークアップやエフェクトを設定する",
            url: "https://vuetifyjs.com/ja/components/data-tables#example-header-cell"
          }, 
          {
            value: false,
            name: 'プログレスバー',
            text: "データをロードしている時にプログレスバーを表示する",
            url: "https://vuetifyjs.com/ja/components/data-tables#example-progress"
          }, 
          {
            value: false,
            name: 'フッター',
            text: "テーブルのフッター。カラムのフィルタや検索など、テーブルに拡張機能を持たせたい時に使う",
            url: "https://vuetifyjs.com/ja/components/data-tables#example-footer"
          },
          {
            value: false,
            name: '行の折りたたみ',
            text: "行を選択した際に、行の開閉をできるようにする",
            url: "https://vuetifyjs.com/ja/components/data-tables#example-expand"
          },  
          {
            value: false,
            name: 'ページネーションの編集',
            text: "ページネーションで使用されるテキストを変更する",
            url: "https://vuetifyjs.com/ja/components/data-tables#example-page-text"
          },  
          {
            value: false,
            name: '行の選択',
            text: "行を選択可能にして、行に対してアクションを実行できる",
            url: "https://vuetifyjs.com/ja/components/data-tables#example-select"
          },  
          {
            value: false,
            name: '行の検索',
            text: "検索機能をつける",
            url: "https://vuetifyjs.com/ja/components/data-tables#example-search"
          },  
          {
            value: false,
            name: 'アイコン',
            text: "ページネーションで、ページ移動のボタンをアイコンにする",
            url: "https://vuetifyjs.com/ja/components/data-tables#example-custom-icons"
          },  
          {
            value: false,
            name: '外部ページネーション',
            text: "テーブル外部からページネーションを制御する",
            url: "https://vuetifyjs.com/ja/components/data-tables#example-paginate"
          },  
          {
            value: false,
            name: '外部ソート',
            text: "テーブル外部からソートを制御する",
            url: "https://vuetifyjs.com/ja/components/data-tables#example-sort"
          },  
          {
            value: false,
            name: 'サーバサイドからのページネーション・ソート',
            text: "バックエンドから情報を読み込み、結果を表示する前にページネーションやソートを適用する",
            url: "https://vuetifyjs.com/ja/components/data-tables#example-server"
          },  
          {
            value: false,
            name: 'ヘッダーの非表示',
            text: "ヘッダーなしのテーブルを作成する",
            url: "https://vuetifyjs.com/ja/components/data-tables#example-headerless"
          },  
          {
            value: false,
            name: 'インライン編集',
            text: "テーブル内部でインライン編集する",
            url: "https://vuetifyjs.com/ja/components/data-tables#example-editdialog"
          },  
          {
            value: false,
            name: '各行の編集',
            text: "行の新規追加・編集・削除をする",
            url: "https://vuetifyjs.com/ja/components/data-tables#example-crud"
          },  
          {
            value: false,
            name: 'イテレータ',
            text: "テーブルと似ているコンポーネント。データの表示を細かくカスタマイズできる",
            url: "https://vuetifyjs.com/ja/components/data-iterator"
          },  
        ],
        stepper_list: [
          {
            value: false,
            name: '編集可能なステップ',
            text: "編集可能なステップなら、ユーザーの選択で移動できる",
            url: "https://vuetifyjs.com/ja/components/steppers#example-editable"
          },  
          {
            value: false,
            name: '編集不可能なステップ',
            text: "ユーザーの選択で移動することはできず、ステップは直線的に進行する",
            url: "https://vuetifyjs.com/ja/components/steppers#example-non-editable"
          },  
          {
            value: false,
            name: 'オプションステップ',
            text: "サブテキストを読み込む",
            url: "https://vuetifyjs.com/ja/components/steppers#example-optional"
          },  
          {
            value: false,
            name: '水平ステップ',
            text: "定義されたステップを経て、x軸に沿って進行する",
            url: "https://vuetifyjs.com/ja/components/steppers#example-horizontal"
          }, 
          {
            value: false,
            name: '垂直ステップ',
            text: "定義されたステップを経て、y軸に沿って進行する",
            url: "https://vuetifyjs.com/ja/components/steppers#example-vertical"
          },  
          {
            value: false,
            name: 'リニアステップ',
            text: "常に定義されたステップで進行する",
            url: "https://vuetifyjs.com/ja/components/steppers#example-linear"
          },  
          {
            value: false,
            name: '非リニアステップ',
            text: "ユーザーが選択した順番でステップが進行する",
            url: "https://vuetifyjs.com/ja/components/steppers#example-non-linear"
          },  
          {
            value: false,
            name: 'エラー表示',
            text: "エラーが起きた際に、それを表示する",
            url: "https://vuetifyjs.com/ja/components/steppers#example-error"
          },  
          {
            value: false,
            name: '代替ラベルによるエラー表示',
            text: "エラー状態を代替ラベルスタイルに適用する",
            url: "https://vuetifyjs.com/ja/components/steppers#example-alternate-error"
          },  
          {
            value: false,
            name: 'ダイナミックなステップ',
            text: "ユーザーの操作で、動的にステップを追加・削除する",
            url: "https://vuetifyjs.com/ja/components/steppers#example-dynamic"
          },  
        ],
        card_list: [
          {
            value: false,
            name: 'テキスト付きメディア',
            text: "画像上などの、背景にテキストを表示する",
            url: "https://vuetifyjs.com/ja/components/cards#example-media-with-text"
          },  
          {
            value: false,
            name: '水平型カード',
            text: "水平型にカスタマイズされたカード",
            url: "https://vuetifyjs.com/ja/components/cards#example-horizontal"
          },  
          {
            value: false,
            name: 'グリッドリスト',
            text: "グリッドを使って、カードのレイアウトを整える",
            url: "https://vuetifyjs.com/ja/components/cards#example-grids"
          },  
          {
            value: false,
            name: '開閉可能なテキストの追加',
            text: "選択するまで閉じられた状態の補助的なテキストを追加する",
            url: "https://vuetifyjs.com/ja/components/cards#example-custom-actions"
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