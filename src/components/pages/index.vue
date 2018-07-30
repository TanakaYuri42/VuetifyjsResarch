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
            <v-card-text class="grey lighten-3">
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
            <Toolbar/>
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
            <Table/>
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
            <div>
              <v-container fluid grid-list-md>
                <v-data-iterator
                  :items="items_iterator"
                  :rows-per-page-items="rowsPerPageItems"
                  :pagination.sync="pagination"
                  content-tag="v-layout"
                  row
                  wrap
                >
                  <v-flex
                    slot="item"
                    slot-scope="props"
                    xs12
                    sm6
                    md4
                    lg3
                  >
                    <v-card style="border:solid 1px #ddd;">
                      <v-card-title><h4>{{ props.item.name }}</h4></v-card-title>
                      <v-divider></v-divider>
                      <v-list dense>
                        <v-list-tile>
                          <v-list-tile-content>Calories:</v-list-tile-content>
                          <v-list-tile-content class="align-end">{{ props.item.calories }}</v-list-tile-content>
                        </v-list-tile>
                        <v-list-tile>
                          <v-list-tile-content>Fat:</v-list-tile-content>
                          <v-list-tile-content class="align-end">{{ props.item.fat }}</v-list-tile-content>
                        </v-list-tile>
                        <v-list-tile>
                          <v-list-tile-content>Carbs:</v-list-tile-content>
                          <v-list-tile-content class="align-end">{{ props.item.carbs }}</v-list-tile-content>
                        </v-list-tile>
                      </v-list>
                    </v-card>
                  </v-flex>
                </v-data-iterator>
              </v-container>
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
            <Card/>
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
                  v-for="item in items_bread"
                  :key="item.text"
                  :disabled="item.disabled"
                >
                  {{ item.text }}
                </v-breadcrumbs-item>
              </v-breadcrumbs>
              <v-breadcrumbs style="display:inline;">
                <v-icon slot="divider">forward</v-icon>
                <v-breadcrumbs-item
                  v-for="item in items_bread"
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
            <Dialog/>
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
            <Pagination/>
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
            <v-container style="padding-top:20px;">
              <v-layout>
                <v-flex xs6>
                  <v-date-picker v-model="picker"></v-date-picker>
                </v-flex>
                <v-flex xs6>
                  <v-time-picker v-model="e4" color="green lighten-1"></v-time-picker>
                </v-flex>
              </v-layout>
            </v-container>
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
            <Tabs/>
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
            <Panel/>
          </v-card-text>
        </v-card>
      </v-expansion-panel-content>

      <v-expansion-panel-content>
        <div slot="header">アバター</div>
        <v-card>
          <v-card-text>
            <div style="padding-bottom:20px;">
              基本的な概要は「
              <a href="https://vuetifyjs.com/ja/components/avatars" target="_blank">
                v-avatar
              </a>
              」参照<br>
              ユーザーの操作に合わせて、動的に要素のサイズ変更や角丸処理を行う
            </div>
            <v-divider></v-divider>
            <v-container grid-list-md>
              <v-layout row wrap>
                  <v-flex xs12 sm6 md4>
                  <v-slider
                    v-model="slider"
                    :min="16"
                    :max="200"
                    label="Size"
                    thumb-label
                  ></v-slider>
                  <v-switch
                    v-model="tile"
                    label="Tile"
                  ></v-switch>
                </v-flex>

                <v-flex
                  xs12
                  sm6
                  md8
                  align-center
                  justify-center
                  layout
                  text-xs-center
                >
                  <v-avatar
                    :tile="tile"
                    :size="avatarSize"
                    color="blue"
                  >
                  </v-avatar>
                </v-flex>
              </v-layout>
            </v-container>
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
            <div>
                <v-btn
                block
                color="primary"
                dark
                @click="snackbar = true"
              >
                Click me!
              </v-btn>

              <v-snackbar
                v-model="snackbar"
                :bottom="y === 'bottom'"
                :left="x === 'left'"
                :multi-line="mode === 'multi-line'"
                :right="x === 'right'"
                :timeout="timeout"
                :top="y === 'top'"
                :vertical="mode === 'vertical'"
              >
                {{ text }}
                <v-btn
                  color="pink"
                  flat
                  @click="snackbar = false"
                >
                  Close
                </v-btn>
              </v-snackbar>
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
            <div>
              <v-bottom-sheet v-model="sheet">
                <v-btn
                  slot="activator"
                  color="purple"
                  dark
                >
                  Click me
                </v-btn>

                <v-list>
                  <v-subheader>Open in</v-subheader>
                  <v-list-tile
                    v-for="tile in tiles"
                    :key="tile.title"
                    @click="sheet = false"
                  >
                    <v-list-tile-avatar>
                      <v-avatar size="32px" tile>
                        <img
                          :src="`https://cdn.vuetifyjs.com/images/bottom-sheets/${tile.img}`"
                          :alt="tile.title"
                        >
                      </v-avatar>
                    </v-list-tile-avatar>
                    <v-list-tile-title>{{ tile.title }}</v-list-tile-title>
                  </v-list-tile>
                </v-list>
              </v-bottom-sheet>
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
            <div>
              <v-carousel>
                <v-carousel-item
                  v-for="(item,i) in items_calousel"
                  :key="i"
                  :src="item.src"
                ></v-carousel-item>
              </v-carousel>
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
            <Stepper/>
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
import Dialog from './index_table_data/dialog_table'
import Pagination from './index_table_data/pagination_table'
import Panel from './index_table_data/panel_table'
import Tabs from './index_table_data/tabs_table'
import Stepper from './index_table_data/stepper_table'
import Card from './index_table_data/card_table'
import Table from './index_table_data/table_table'
import Toolbar from './index_table_data/toolbar_table'

  export default {
    components: {
      ButtonTable,
      Icon,
      Alert,
      Badge,
      Chip,
      ProgressC,
      ProgressL,
      Dialog,
      Pagination,
      Panel,
      Tabs,
      Stepper,
      Card,
      Table,
      Toolbar,
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
        slider: 56,
        tile: false,
         snackbar: false,
        y: 'top',
        x: null,
        mode: '',
        timeout: 6000,
        text: 'Hello, I\'m a snackbar',
        sheet: false,
        tiles: [
          { img: 'keep.png', title: 'Keep' },
          { img: 'inbox.png', title: 'Inbox' },
          { img: 'hangouts.png', title: 'Hangouts' },
          { img: 'messenger.png', title: 'Messenger' },
          { img: 'google.png', title: 'Google+' }
        ],
        rowsPerPageItems: [4, 8, 12],
        pagination: {
          rowsPerPage: 4
        },
        items_bread: [
          {
            text: 'Dashboard',
            disabled: false
          },
          {
            text: 'Link 1',
            disabled: false
          },
          {
            text: 'Link 2',
            disabled: true
          }
        ],
        items_iterator: [
          {
            value: false,
            name: 'Frozen Yogurt',
            calories: 159,
            fat: 6.0,
            carbs: 24,
            protein: 4.0,
            sodium: 87,
            calcium: '14%',
            iron: '1%'
          },
          {
            value: false,
            name: 'Ice cream sandwich',
            calories: 237,
            fat: 9.0,
            carbs: 37,
            protein: 4.3,
            sodium: 129,
            calcium: '8%',
            iron: '1%'
          },
          {
            value: false,
            name: 'Eclair',
            calories: 262,
            fat: 16.0,
            carbs: 23,
            protein: 6.0,
            sodium: 337,
            calcium: '6%',
            iron: '7%'
          },
          {
            value: false,
            name: 'Cupcake',
            calories: 305,
            fat: 3.7,
            carbs: 67,
            protein: 4.3,
            sodium: 413,
            calcium: '3%',
            iron: '8%'
          },
          {
            value: false,
            name: 'Gingerbread',
            calories: 356,
            fat: 16.0,
            carbs: 49,
            protein: 3.9,
            sodium: 327,
            calcium: '7%',
            iron: '16%'
          },
          {
            value: false,
            name: 'Jelly bean',
            calories: 375,
            fat: 0.0,
            carbs: 94,
            protein: 0.0,
            sodium: 50,
            calcium: '0%',
            iron: '0%'
          },
          {
            value: false,
            name: 'Lollipop',
            calories: 392,
            fat: 0.2,
            carbs: 98,
            protein: 0,
            sodium: 38,
            calcium: '0%',
            iron: '2%'
          },
          {
            value: false,
            name: 'Honeycomb',
            calories: 408,
            fat: 3.2,
            carbs: 87,
            protein: 6.5,
            sodium: 562,
            calcium: '0%',
            iron: '45%'
          },
          {
            value: false,
            name: 'Donut',
            calories: 452,
            fat: 25.0,
            carbs: 51,
            protein: 4.9,
            sodium: 326,
            calcium: '2%',
            iron: '22%'
          },
          {
            value: false,
            name: 'KitKat',
            calories: 518,
            fat: 26.0,
            carbs: 65,
            protein: 7,
            sodium: 54,
            calcium: '12%',
            iron: '6%'
          }
        ],
        items_calousel: [
          {
            src: 'https://cdn.vuetifyjs.com/images/carousel/squirrel.jpg'
          },
          {
            src: 'https://cdn.vuetifyjs.com/images/carousel/sky.jpg'
          },
          {
            src: 'https://cdn.vuetifyjs.com/images/carousel/bird.jpg'
          },
          {
            src: 'https://cdn.vuetifyjs.com/images/carousel/planet.jpg'
          }
        ]
      }
    },
    computed: {
      avatarSize () {
        return `${this.slider}px`
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