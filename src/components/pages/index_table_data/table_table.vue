<template>
  <v-data-table
    :headers="headers"
    :items="table_list"
    hide-actions
    class="elevation-1 table" 
    hide-headers="true"
    disable-initial-sort="true"
  >
    <template slot="items" slot-scope="props">
      <tr>
          <td>
            <a :href="props.item.url" target="_blank">
              {{ props.item.name }}
            </a>
          </td>
          <td>{{ props.item.text }}</td>
      </tr>

      <tr>
        <td v-if="props.item.num == 1" colspan="2" class="pt-3 pb-3">
          <v-data-table
            :headers="headers"
            :items="desserts1"
            hide-actions
            class="elevation-1"
          >
            <template slot="items" slot-scope="props">
              <td>{{ props.item.name }}</td>
              <td class="text-xs-right">{{ props.item.calories }}</td>
              <td class="text-xs-right">{{ props.item.fat }}</td>
              <td class="text-xs-right">{{ props.item.carbs }}</td>
              <td class="text-xs-right">{{ props.item.protein }}</td>
              <td class="text-xs-right">{{ props.item.iron }}</td>
            </template>
            <template slot="no-data">
              <v-alert :value="true" color="error" icon="warning">
                Sorry, nothing to display here :(
              </v-alert>
            </template>
          </v-data-table>
        </td>


        <td v-else-if="props.item.num == 2" colspan="2" class="pt-3 pb-3">
          <v-data-table
            :headers="headers"
            :items="desserts"
            class="elevation-1"
          >
            <template slot="headerCell" slot-scope="props">
              <v-tooltip bottom>
                <span slot="activator">
                  {{ props.header.text }}
                </span>
                <span>
                  {{ props.header.text }}
                </span>
              </v-tooltip>
            </template>
            <template slot="items" slot-scope="props">
              <td>{{ props.item.name }}</td>
              <td class="text-xs-right">{{ props.item.calories }}</td>
              <td class="text-xs-right">{{ props.item.fat }}</td>
              <td class="text-xs-right">{{ props.item.carbs }}</td>
              <td class="text-xs-right">{{ props.item.protein }}</td>
              <td class="text-xs-right">{{ props.item.iron }}</td>
            </template>
          </v-data-table>
        </td>


        <td v-else-if="props.item.num == 3" colspan="2" class="pt-3 pb-3">
          <v-data-table
            :headers="headers"
            :items="desserts"
            :loading="true"
            class="elevation-1"
          >
            <v-progress-linear slot="progress" color="blue" indeterminate></v-progress-linear>
            <template slot="items" slot-scope="props">
              <td>{{ props.item.name }}</td>
              <td class="text-xs-right">{{ props.item.calories }}</td>
              <td class="text-xs-right">{{ props.item.fat }}</td>
              <td class="text-xs-right">{{ props.item.carbs }}</td>
              <td class="text-xs-right">{{ props.item.protein }}</td>
              <td class="text-xs-right">{{ props.item.iron }}</td>
            </template>
          </v-data-table>
        </td>


        <td v-else-if="props.item.num == 4" colspan="2" class="pt-3 pb-3">
          <v-data-table
            :headers="headers"
            :items="desserts"
            class="elevation-1"
          >
            <template slot="items" slot-scope="props">
              <td>{{ props.item.name }}</td>
              <td class="text-xs-right">{{ props.item.calories }}</td>
              <td class="text-xs-right">{{ props.item.fat }}</td>
              <td class="text-xs-right">{{ props.item.carbs }}</td>
              <td class="text-xs-right">{{ props.item.protein }}</td>
              <td class="text-xs-right">{{ props.item.iron }}</td>
            </template>
            <template slot="footer">
              <td colspan="100%">
                <strong>This is an extra footer</strong>
              </td>
            </template>
          </v-data-table>
        </td>


        <td v-else-if="props.item.num == 5" colspan="2" class="pt-3 pb-3">
          <v-data-table
            :headers="headers"
            :items="desserts"
            hide-actions
            item-key="name"
          >
            <template slot="items" slot-scope="props">
              <tr @click="props.expanded = !props.expanded">
                <td>{{ props.item.name }}</td>
                <td class="text-xs-right">{{ props.item.calories }}</td>
                <td class="text-xs-right">{{ props.item.fat }}</td>
                <td class="text-xs-right">{{ props.item.carbs }}</td>
                <td class="text-xs-right">{{ props.item.protein }}</td>
                <td class="text-xs-right">{{ props.item.iron }}</td>
              </tr>
            </template>
            <template slot="expand" slot-scope="props">
              <v-card flat>
                <v-card-text>Peek-a-boo!</v-card-text>
              </v-card>
            </template>
          </v-data-table>
        </td>


        <td v-else-if="props.item.num == 6" colspan="2" class="pt-3 pb-3">
          <v-data-table
            :headers="headers"
            :items="desserts"
            class="elevation-1"
          >
            <template slot="items" slot-scope="props">
              <td>{{ props.item.name }}</td>
              <td class="text-xs-right">{{ props.item.calories }}</td>
              <td class="text-xs-right">{{ props.item.fat }}</td>
              <td class="text-xs-right">{{ props.item.carbs }}</td>
              <td class="text-xs-right">{{ props.item.protein }}</td>
              <td class="text-xs-right">{{ props.item.iron }}</td>
            </template>
            <template slot="pageText" slot-scope="props">
              Lignes {{ props.pageStart }} - {{ props.pageStop }} de {{ props.itemsLength }}
            </template>
          </v-data-table>
        </td>


        <td v-else-if="props.item.num == 7" colspan="2" class="pt-3 pb-3">
          <v-data-table
            :headers="headers"
            :items="desserts"
            :search="search"
            v-model="selected"
            item-key="name"
            select-all
            class="elevation-1"
          >
            <template slot="headerCell" slot-scope="props">
              <v-tooltip bottom>
                <span slot="activator">
                  {{ props.header.text }}
                </span>
                <span>
                  {{ props.header.text }}
                </span>
              </v-tooltip>
            </template>
            <template slot="items" slot-scope="props">
              <td>
                <v-checkbox
                  v-model="props.selected"
                  primary
                  hide-details
                ></v-checkbox>
              </td>
              <td>{{ props.item.name }}</td>
              <td class="text-xs-right">{{ props.item.calories }}</td>
              <td class="text-xs-right">{{ props.item.fat }}</td>
              <td class="text-xs-right">{{ props.item.carbs }}</td>
              <td class="text-xs-right">{{ props.item.protein }}</td>
              <td class="text-xs-right">{{ props.item.iron }}</td>
            </template>
          </v-data-table>
        </td>


        <td v-else-if="props.item.num == 8" colspan="2" class="pt-3 pb-3">
          <v-card>
            <v-card-title>
              Nutrition
              <v-spacer></v-spacer>
              <v-text-field
                v-model="search2"
                append-icon="search2"
                label="Search"
                single-line
                hide-details
              ></v-text-field>
            </v-card-title>
            <v-data-table
              :headers="headers"
              :items="desserts"
              :search="search2"
            >
              <template slot="items" slot-scope="props">
                <td>{{ props.item.name }}</td>
                <td class="text-xs-right">{{ props.item.calories }}</td>
                <td class="text-xs-right">{{ props.item.fat }}</td>
                <td class="text-xs-right">{{ props.item.carbs }}</td>
                <td class="text-xs-right">{{ props.item.protein }}</td>
                <td class="text-xs-right">{{ props.item.iron }}</td>
              </template>
              <v-alert slot="no-results" :value="true" color="error" icon="warning">
                Your search for "{{ search2 }}" found no results.
              </v-alert>
            </v-data-table>
          </v-card>
        </td>


        <td v-else-if="props.item.num == 9" colspan="2" class="pt-3 pb-3">
          <v-data-table
            :headers="headers"
            :items="desserts"
            class="elevation-1"
            prev-icon="mdi-menu-left"
            next-icon="mdi-menu-right"
            sort-icon="mdi-menu-down"
          >
            <template slot="items" slot-scope="props">
              <td>{{ props.item.name }}</td>
              <td class="text-xs-right">{{ props.item.calories }}</td>
              <td class="text-xs-right">{{ props.item.fat }}</td>
              <td class="text-xs-right">{{ props.item.carbs }}</td>
              <td class="text-xs-right">{{ props.item.protein }}</td>
              <td class="text-xs-right">{{ props.item.iron }}</td>
            </template>
          </v-data-table>
        </td>


        <td v-else-if="props.item.num == 10" colspan="2" class="pt-3 pb-3">
          <div>
            <v-data-table
              :headers="headers"
              :items="desserts"
              :search="search10"
              :pagination.sync="pagination10"
              hide-actions
              class="elevation-1"
            >
              <template slot="headerCell" slot-scope="props">
                <v-tooltip bottom>
                  <span slot="activator">
                    {{ props.header.text }}
                  </span>
                  <span>
                    {{ props.header.text }}
                  </span>
                </v-tooltip>
              </template>
              <template slot="items" slot-scope="props">
                <td>{{ props.item.name }}</td>
                <td class="text-xs-right">{{ props.item.calories }}</td>
                <td class="text-xs-right">{{ props.item.fat }}</td>
                <td class="text-xs-right">{{ props.item.carbs }}</td>
                <td class="text-xs-right">{{ props.item.protein }}</td>
                <td class="text-xs-right">{{ props.item.iron }}</td>
              </template>
            </v-data-table>
            <div class="text-xs-center pt-2">
              <v-pagination v-model="pagination10.page" :length="pages"></v-pagination>
            </div>
          </div>
        </td>


        <td v-else-if="props.item.num == 11" colspan="2" class="pt-3 pb-3">
          <div>
            <v-data-table
              :headers="headers"
              :items="desserts"
              :search="search11"
              :pagination.sync="pagination11"
              class="elevation-1"
            >
              <template slot="items" slot-scope="props">
                <td>{{ props.item.name }}</td>
                <td class="text-xs-right">{{ props.item.calories }}</td>
                <td class="text-xs-right">{{ props.item.fat }}</td>
                <td class="text-xs-right">{{ props.item.carbs }}</td>
                <td class="text-xs-right">{{ props.item.protein }}</td>
                <td class="text-xs-right">{{ props.item.iron }}</td>
              </template>
            </v-data-table>
            <div class="text-xs-center pt-2">
              <v-btn color="primary" @click.native="toggleOrder">Toggle sort order</v-btn>
              <v-btn color="primary" @click.native="nextSort">Sort next column</v-btn>
            </div>
          </div>
        </td>


        <td v-else-if="props.item.num == 12" colspan="2" class="pt-3 pb-3">
          <div>
            <v-data-table
              :headers="headers"
              :items="desserts12"
              :pagination.sync="pagination12"
              :total-items="totalDesserts"
              :loading="loading12"
              class="elevation-1"
            >
              <template slot="items" slot-scope="props">
                <td>{{ props.item.name }}</td>
                <td class="text-xs-right">{{ props.item.calories }}</td>
                <td class="text-xs-right">{{ props.item.fat }}</td>
                <td class="text-xs-right">{{ props.item.carbs }}</td>
                <td class="text-xs-right">{{ props.item.protein }}</td>
                <td class="text-xs-right">{{ props.item.iron }}</td>
              </template>
            </v-data-table>
          </div>
        </td>


        <td v-else-if="props.item.num == 13" colspan="2" class="pt-3 pb-3">
          <v-data-table
            :items="desserts"
            class="elevation-1"
            hide-actions
            hide-headers
          >
            <template slot="items" slot-scope="props">
              <td>{{ props.item.name }}</td>
              <td class="text-xs-right">{{ props.item.calories }}</td>
              <td class="text-xs-right">{{ props.item.fat }}</td>
              <td class="text-xs-right">{{ props.item.carbs }}</td>
              <td class="text-xs-right">{{ props.item.protein }}</td>
              <td class="text-xs-right">{{ props.item.iron }}</td>
            </template>
          </v-data-table>
        </td>


        <td v-else-if="props.item.num == 14" colspan="2" class="pt-3 pb-3">
          <div>
            <v-data-table
              :headers="headers"
              :items="desserts14"
            >
              <template slot="items" slot-scope="props">
                <td>
                  <v-edit-dialog
                    :return-value.sync="props.item.name"
                    lazy
                    @save="save"
                    @cancel="cancel"
                    @open="open"
                    @close="close"
                  > {{ props.item.name }}
                    <v-text-field
                      slot="input"
                      v-model="props.item.name"
                      :rules="[max25chars]"
                      label="Edit"
                      single-line
                      counter
                    ></v-text-field>
                  </v-edit-dialog>
                </td>
                <td class="text-xs-right">{{ props.item.calories }}</td>
                <td class="text-xs-right">{{ props.item.fat }}</td>
                <td class="text-xs-right">{{ props.item.carbs }}</td>
                <td class="text-xs-right">{{ props.item.protein }}</td>
                <td class="text-xs-right">
                  <v-edit-dialog
                    :return-value.sync="props.item.iron"
                    large
                    lazy
                    persistent
                    @save="save"
                    @cancel="cancel"
                    @open="open"
                    @close="close"
                  >
                    <div>{{ props.item.iron }}</div>
                    <div slot="input" class="mt-3 title">Update Iron</div>
                    <v-text-field
                      slot="input"
                      v-model="props.item.iron"
                      :rules="[max25chars]"
                      label="Edit"
                      single-line
                      counter
                      autofocus
                    ></v-text-field>
                  </v-edit-dialog>
                </td>
              </template>
              <template slot="pageText" slot-scope="{ pageStart, pageStop }">
                From {{ pageStart }} to {{ pageStop }}
              </template>
            </v-data-table>

            <v-snackbar v-model="snack" :timeout="3000" :color="snackColor">
              {{ snackText }}
              <v-btn flat @click="snack = false">Close</v-btn>
            </v-snackbar>
          </div>
        </td>


        <td v-else-if="props.item.num == 15" colspan="2" class="pt-3 pb-3">
          <div>
            <v-toolbar flat color="white">
              <v-toolbar-title>My CRUD</v-toolbar-title>
              <v-divider
                class="mx-2"
                inset
                vertical
              ></v-divider>
              <v-spacer></v-spacer>
              <v-dialog v-model="dialog" max-width="500px">
                <v-btn slot="activator" color="primary" dark class="mb-2">New Item</v-btn>
                <v-card>
                  <v-card-title>
                    <span class="headline">{{ formTitle }}</span>
                  </v-card-title>

                  <v-card-text>
                    <v-container grid-list-md>
                      <v-layout wrap>
                        <v-flex xs12 sm6 md4>
                          <v-text-field v-model="editedItem.name" label="Dessert name"></v-text-field>
                        </v-flex>
                        <v-flex xs12 sm6 md4>
                          <v-text-field v-model="editedItem.calories" label="Calories"></v-text-field>
                        </v-flex>
                        <v-flex xs12 sm6 md4>
                          <v-text-field v-model="editedItem.fat" label="Fat (g)"></v-text-field>
                        </v-flex>
                        <v-flex xs12 sm6 md4>
                          <v-text-field v-model="editedItem.carbs" label="Carbs (g)"></v-text-field>
                        </v-flex>
                        <v-flex xs12 sm6 md4>
                          <v-text-field v-model="editedItem.protein" label="Protein (g)"></v-text-field>
                        </v-flex>
                      </v-layout>
                    </v-container>
                  </v-card-text>

                  <v-card-actions>
                    <v-spacer></v-spacer>
                    <v-btn color="blue darken-1" flat @click.native="close">Cancel</v-btn>
                    <v-btn color="blue darken-1" flat @click.native="save">Save</v-btn>
                  </v-card-actions>
                </v-card>
              </v-dialog>
            </v-toolbar>
            <v-data-table
              :headers="headers"
              :items="desserts15"
              hide-actions
              class="elevation-1"
            >
              <template slot="items" slot-scope="props">
                <td>{{ props.item.name }}</td>
                <td class="text-xs-right">{{ props.item.calories }}</td>
                <td class="text-xs-right">{{ props.item.fat }}</td>
                <td class="text-xs-right">{{ props.item.carbs }}</td>
                <td class="text-xs-right">{{ props.item.protein }}</td>
                <td class="justify-center layout px-0">
                  <v-icon
                    small
                    class="mr-2"
                    @click="editItem(props.item)"
                  >
                    edit
                  </v-icon>
                  <v-icon
                    small
                    @click="deleteItem(props.item)"
                  >
                    delete
                  </v-icon>
                </td>
              </template>
              <template slot="no-data">
                <v-btn color="primary" @click="initialize">Reset</v-btn>
              </template>
            </v-data-table>
          </div>
        </td>


        <td v-else-if="props.item.num == 16" colspan="2" class="pt-3 pb-3">
          <div>
            <v-container fluid grid-list-md>
              <v-data-iterator
                :items="items_iterator"
                :rows-per-page-items="rowsPerPageItems"
                :pagination.sync="pagination16"
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
        </td>

      </tr>
    
    </template>
  </v-data-table>
</template>

<script>

  export default {
    data () {
      return {
        table_list: [
          {
            value: false,
            name: 'データがない時の設定',
            text: "データが存在しない時に表示するhtmlを設定する",
            url: "https://vuetifyjs.com/ja/components/data-tables#example-no-data",
            num: 1,
          }, 
          {
            value: false,
            name: 'ヘッダーのセルごとの共通設定',
            text: "ヘッダーのセルごとに共通のマークアップやエフェクトを設定する",
            url: "https://vuetifyjs.com/ja/components/data-tables#example-header-cell",
            num: 2
          }, 
          {
            value: false,
            name: 'プログレスバー',
            text: "データをロードしている時にプログレスバーを表示する",
            url: "https://vuetifyjs.com/ja/components/data-tables#example-progress",
            num: 3
          }, 
          {
            value: false,
            name: 'フッター',
            text: "テーブルのフッター。カラムのフィルタや検索など、テーブルに拡張機能を持たせたい時に使う",
            url: "https://vuetifyjs.com/ja/components/data-tables#example-footer",
            num: 4,
          },
          {
            value: false,
            name: '行の折りたたみ',
            text: "行を選択した際に、行の開閉をできるようにする",
            url: "https://vuetifyjs.com/ja/components/data-tables#example-expand",
            num: 5,
          },  
          {
            value: false,
            name: 'ページネーションの編集',
            text: "ページネーションで使用されるテキストを変更する",
            url: "https://vuetifyjs.com/ja/components/data-tables#example-page-text",
            num: 6,
          },  
          {
            value: false,
            name: '行の選択',
            text: "行を選択可能にして、行に対してアクションを実行できる",
            url: "https://vuetifyjs.com/ja/components/data-tables#example-select",
            num: 7
          },  
          {
            value: false,
            name: '行の検索',
            text: "検索機能をつける",
            url: "https://vuetifyjs.com/ja/components/data-tables#example-search",
            num: 8
          },  
          {
            value: false,
            name: 'アイコン',
            text: "ページネーションで、ページ移動のボタンをアイコンにする",
            url: "https://vuetifyjs.com/ja/components/data-tables#example-custom-icons",
            num: 9,
          },  
          {
            value: false,
            name: '外部ページネーション',
            text: "テーブル外部からページネーションを制御する",
            url: "https://vuetifyjs.com/ja/components/data-tables#example-paginate",
            num: 10
          },  
          {
            value: false,
            name: '外部ソート',
            text: "テーブル外部からソートを制御する",
            url: "https://vuetifyjs.com/ja/components/data-tables#example-sort",
            num: 11,
          },  
          {
            value: false,
            name: 'サーバサイドからのページネーション・ソート',
            text: "バックエンドから情報を読み込み、結果を表示する前にページネーションやソートを適用する",
            url: "https://vuetifyjs.com/ja/components/data-tables#example-server",
            num: 12,
          },  
          {
            value: false,
            name: 'ヘッダーの非表示',
            text: "ヘッダーなしのテーブルを作成する",
            url: "https://vuetifyjs.com/ja/components/data-tables#example-headerless",
            num: 13,
          },  
          {
            value: false,
            name: 'インライン編集',
            text: "テーブル内部でインライン編集する",
            url: "https://vuetifyjs.com/ja/components/data-tables#example-editdialog",
            num: 14,
          },  
          {
            value: false,
            name: '各行の編集',
            text: "行の新規追加・編集・削除をする",
            url: "https://vuetifyjs.com/ja/components/data-tables#example-crud",
            num: 15,
          },  
          {
            value: false,
            name: 'イテレータ',
            text: "テーブルと似ているコンポーネント。データの表示を細かくカスタマイズできる",
            url: "https://vuetifyjs.com/ja/components/data-iterator",
            num: 16
          },  
        ],
        headers: [
          {
            text: 'Dessert (100g serving)',
            align: 'left',
            sortable: false,
            value: 'name'
          },
          { text: 'Calories', value: 'calories' },
          { text: 'Fat (g)', value: 'fat' },
          { text: 'Carbs (g)', value: 'carbs' },
          { text: 'Protein (g)', value: 'protein' },
          { text: 'Iron (%)', value: 'iron' }
        ],
        desserts1: [
        ],
        desserts: [
          {
            value: false,
            name: 'Frozen Yogurt',
            calories: 159,
            fat: 6.0,
            carbs: 24,
            protein: 4.0,
            iron: '1%'
          },
          {
            value: false,
            name: 'Ice cream sandwich',
            calories: 237,
            fat: 9.0,
            carbs: 37,
            protein: 4.3,
            iron: '1%'
          },
          {
            value: false,
            name: 'Eclair',
            calories: 262,
            fat: 16.0,
            carbs: 23,
            protein: 6.0,
            iron: '7%'
          },
          {
            value: false,
            name: 'Cupcake',
            calories: 305,
            fat: 3.7,
            carbs: 67,
            protein: 4.3,
            iron: '8%'
          },
          {
            value: false,
            name: 'Gingerbread',
            calories: 356,
            fat: 16.0,
            carbs: 49,
            protein: 3.9,
            iron: '16%'
          },
          {
            value: false,
            name: 'Jelly bean',
            calories: 375,
            fat: 0.0,
            carbs: 94,
            protein: 0.0,
            iron: '0%'
          },
          {
            value: false,
            name: 'Lollipop',
            calories: 392,
            fat: 0.2,
            carbs: 98,
            protein: 0,
            iron: '2%'
          },
          {
            value: false,
            name: 'Honeycomb',
            calories: 408,
            fat: 3.2,
            carbs: 87,
            protein: 6.5,
            iron: '45%'
          },
          {
            value: false,
            name: 'Donut',
            calories: 452,
            fat: 25.0,
            carbs: 51,
            protein: 4.9,
            iron: '22%'
          },
          {
            value: false,
            name: 'KitKat',
            calories: 518,
            fat: 26.0,
            carbs: 65,
            protein: 7,
            iron: '6%'
          }
        ],
        search: '',
        search2: '',
        selected: [],
        search10: '',
        pagination10: {},
        selected10: [],
        search11: '',
        pagination11: {
          sortBy: 'fat'
        },
        selected11: [],
        totalDesserts: 0,
        desserts12: [],
        loading12: true,
        pagination12: {},
        snack: false,
        snackColor: '',
        snackText: '',
        max25chars: (v) => v.length <= 25 || 'Input too long!',
        pagination14: {},
        desserts14: [
          {
            value: false,
            name: 'Frozen Yogurt',
            calories: 159,
            fat: 6.0,
            carbs: 24,
            protein: 4.0,
            iron: '1%'
          },
          {
            value: false,
            name: 'Ice cream sandwich',
            calories: 237,
            fat: 9.0,
            carbs: 37,
            protein: 4.3,
            iron: '1%'
          },
          {
            value: false,
            name: 'Eclair',
            calories: 262,
            fat: 16.0,
            carbs: 23,
            protein: 6.0,
            iron: '7%'
          },
          {
            value: false,
            name: 'Cupcake',
            calories: 305,
            fat: 3.7,
            carbs: 67,
            protein: 4.3,
            iron: '8%'
          },
          {
            value: false,
            name: 'Gingerbread',
            calories: 356,
            fat: 16.0,
            carbs: 49,
            protein: 3.9,
            iron: '16%'
          },
          {
            value: false,
            name: 'Jelly bean',
            calories: 375,
            fat: 0.0,
            carbs: 94,
            protein: 0.0,
            iron: '0%'
          },
          {
            value: false,
            name: 'Lollipop',
            calories: 392,
            fat: 0.2,
            carbs: 98,
            protein: 0,
            iron: '2%'
          },
          {
            value: false,
            name: 'Honeycomb',
            calories: 408,
            fat: 3.2,
            carbs: 87,
            protein: 6.5,
            iron: '45%'
          },
          {
            value: false,
            name: 'Donut',
            calories: 452,
            fat: 25.0,
            carbs: 51,
            protein: 4.9,
            iron: '22%'
          },
          {
            value: false,
            name: 'KitKat',
            calories: 518,
            fat: 26.0,
            carbs: 65,
            protein: 7,
            iron: '6%'
          }
        ],
        dialog: false,
        desserts15: [],
        editedIndex: -1,
        editedItem: {
          name: '',
          calories: 0,
          fat: 0,
          carbs: 0,
          protein: 0
        },
        defaultItem: {
          name: '',
          calories: 0,
          fat: 0,
          carbs: 0,
          protein: 0
        },
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
        rowsPerPageItems: [4, 8, 12],
        pagination16: {
        rowsPerPage: 4
      },
      }
    },
    computed: {
      pages () {
        if (this.pagination10.rowsPerPage == null ||
          this.pagination10.totalItems == null
        ) return 0

        return Math.ceil(this.pagination10.totalItems / this.pagination10.rowsPerPage)
      },
      formTitle () {
        return this.editedIndex === -1 ? 'New Item' : 'Edit Item'
      }
    },

    methods: {
      toggleOrder () {
        this.pagination11.descending = !this.pagination11.descending
      },
      nextSort () {
        let index = this.headers.findIndex(h => h.value === this.pagination11.sortBy)
        index = (index + 1) % this.headers.length
        index = index === 0 ? index + 1 : index
        this.pagination11.sortBy = this.headers[index].value
      },
      getDataFromApi () {
        this.loading = true
        return new Promise((resolve, reject) => {
          const { sortBy, descending, page, rowsPerPage } = this.pagination12

          let items = this.getDesserts()
          const total = items.length

          if (this.pagination12.sortBy) {
            items = items.sort((a, b) => {
              const sortA = a[sortBy]
              const sortB = b[sortBy]

              if (descending) {
                if (sortA < sortB) return 1
                if (sortA > sortB) return -1
                return 0
              } else {
                if (sortA < sortB) return -1
                if (sortA > sortB) return 1
                return 0
              }
            })
          }

          if (rowsPerPage > 0) {
            items = items.slice((page - 1) * rowsPerPage, page * rowsPerPage)
          }

          setTimeout(() => {
            this.loading12 = false
            resolve({
              items,
              total
            })
          }, 1000)
        })
      },
      getDesserts () {
        return [
          {
            value: false,
            name: 'Frozen Yogurt',
            calories: 159,
            fat: 6.0,
            carbs: 24,
            protein: 4.0,
            iron: '1%'
          },
          {
            value: false,
            name: 'Ice cream sandwich',
            calories: 237,
            fat: 9.0,
            carbs: 37,
            protein: 4.3,
            iron: '1%'
          },
          {
            value: false,
            name: 'Eclair',
            calories: 262,
            fat: 16.0,
            carbs: 23,
            protein: 6.0,
            iron: '7%'
          },
          {
            value: false,
            name: 'Cupcake',
            calories: 305,
            fat: 3.7,
            carbs: 67,
            protein: 4.3,
            iron: '8%'
          },
          {
            value: false,
            name: 'Gingerbread',
            calories: 356,
            fat: 16.0,
            carbs: 49,
            protein: 3.9,
            iron: '16%'
          },
          {
            value: false,
            name: 'Jelly bean',
            calories: 375,
            fat: 0.0,
            carbs: 94,
            protein: 0.0,
            iron: '0%'
          },
          {
            value: false,
            name: 'Lollipop',
            calories: 392,
            fat: 0.2,
            carbs: 98,
            protein: 0,
            iron: '2%'
          },
          {
            value: false,
            name: 'Honeycomb',
            calories: 408,
            fat: 3.2,
            carbs: 87,
            protein: 6.5,
            iron: '45%'
          },
          {
            value: false,
            name: 'Donut',
            calories: 452,
            fat: 25.0,
            carbs: 51,
            protein: 4.9,
            iron: '22%'
          },
          {
            value: false,
            name: 'KitKat',
            calories: 518,
            fat: 26.0,
            carbs: 65,
            protein: 7,
            iron: '6%'
          }
        ]
      },
      save () {
        this.snack = true
        this.snackColor = 'success'
        this.snackText = 'Data saved'
      },
      cancel () {
        this.snack = true
        this.snackColor = 'error'
        this.snackText = 'Canceled'
      },
      open () {
        this.snack = true
        this.snackColor = 'info'
        this.snackText = 'Dialog opened'
      },
      close () {
        console.log('Dialog closed')
      },
      initialize () {
        this.desserts15 = [
          {
            name: 'Frozen Yogurt',
            calories: 159,
            fat: 6.0,
            carbs: 24,
            protein: 4.0
          },
          {
            name: 'Ice cream sandwich',
            calories: 237,
            fat: 9.0,
            carbs: 37,
            protein: 4.3
          },
          {
            name: 'Eclair',
            calories: 262,
            fat: 16.0,
            carbs: 23,
            protein: 6.0
          },
          {
            name: 'Cupcake',
            calories: 305,
            fat: 3.7,
            carbs: 67,
            protein: 4.3
          },
          {
            name: 'Gingerbread',
            calories: 356,
            fat: 16.0,
            carbs: 49,
            protein: 3.9
          },
          {
            name: 'Jelly bean',
            calories: 375,
            fat: 0.0,
            carbs: 94,
            protein: 0.0
          },
          {
            name: 'Lollipop',
            calories: 392,
            fat: 0.2,
            carbs: 98,
            protein: 0
          },
          {
            name: 'Honeycomb',
            calories: 408,
            fat: 3.2,
            carbs: 87,
            protein: 6.5
          },
          {
            name: 'Donut',
            calories: 452,
            fat: 25.0,
            carbs: 51,
            protein: 4.9
          },
          {
            name: 'KitKat',
            calories: 518,
            fat: 26.0,
            carbs: 65,
            protein: 7
          }
        ]
      },
      editItem (item) {
        this.editedIndex = this.desserts15.indexOf(item)
        this.editedItem = Object.assign({}, item)
        this.dialog = true
      },

      deleteItem (item) {
        const index = this.desserts15.indexOf(item)
        confirm('Are you sure you want to delete this item?') && this.desserts15.splice(index, 1)
      },

      close () {
        this.dialog = false
        setTimeout(() => {
          this.editedItem = Object.assign({}, this.defaultItem)
          this.editedIndex = -1
        }, 300)
      },

      save () {
        if (this.editedIndex > -1) {
          Object.assign(this.desserts15[this.editedIndex], this.editedItem)
        } else {
          this.desserts15.push(this.editedItem)
        }
        this.close()
      }
    },
    watch: {
      pagination12: {
        handler () {
          this.getDataFromApi()
            .then(data => {
              this.desserts12 = data.items
              this.totalDesserts = data.total
            })
        },
        deep: true
      },
      dialog (val) {
        val || this.close()
      }
    },
    created () {
      this.initialize()
    },
    mounted () {
      this.getDataFromApi()
        .then(data => {
          this.desserts12 = data.items
          this.totalDesserts = data.total
        })
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
