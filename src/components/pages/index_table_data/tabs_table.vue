<template>
  <v-data-table
    :headers="headers"
    :items="tab_list"
    hide-actions
    class="elevation-1" 
    hide-headers="true"
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
        <td v-if="props.item.num == 1" colspan="2" class="px-2 py-3">
          <v-tabs fixed-tabs>
            <v-tab
              v-for="n in 3"
              :key="n"
            >
              Item {{ n }}
            </v-tab>
          </v-tabs>
        </td>

        <td v-else-if="props.item.num == 2" colspan="2" class="px-2 py-3">
          <v-tabs right>
            <v-tab
              v-for="n in 3"
              :key="n"
            >
              Item {{ n }}
            </v-tab>
          </v-tabs>
        </td>

        <td v-else-if="props.item.num == 3" colspan="2" class="px-2 py-3">
          <div>
            <v-toolbar
              color="cyan"
              dark
              tabs
            >
              <v-toolbar-side-icon></v-toolbar-side-icon>
              <v-toolbar-title>Page title</v-toolbar-title>
              <v-spacer></v-spacer>
              <v-btn icon>
                <v-icon>search</v-icon>
              </v-btn>
              <v-btn icon>
                <v-icon>more_vert</v-icon>
              </v-btn>
              <v-tabs
                slot="extension"
                v-model="model3"
                centered
                color="cyan"
                slider-color="yellow"
              >
                <v-tab
                  v-for="i in 3"
                  :key="i"
                  :href="`#tab-${i}`"
                >
                  Item {{ i }}
                </v-tab>
              </v-tabs>
            </v-toolbar>
            <v-tabs-items v-model="model3">
              <v-tab-item
                v-for="i in 3"
                :id="`tab-${i}`"
                :key="i"
              >
                <v-card flat>
                  <v-card-text v-text="text"></v-card-text>
                </v-card>
              </v-tab-item>
            </v-tabs-items>
          </div>
        </td>

        <td v-else-if="props.item.num == 4" colspan="2" class="px-2 py-3">
          <div>
            <v-toolbar
              color="purple"
              dark
              tabs
            >
              <v-text-field
                append-icon="mic"
                class="mx-3"
                flat
                label="Search"
                prepend-inner-icon="search"
                solo-inverted
              ></v-text-field>
              <v-tabs
                slot="extension"
                v-model="tabs4"
                centered
                color="transparent"
                slider-color="white"
              >
                <v-tab
                  v-for="n in 3"
                  :key="n"
                >
                  Item {{ n }}
                </v-tab>
              </v-tabs>
            </v-toolbar>
            <v-tabs-items v-model="tabs4">
              <v-tab-item
                v-for="n in 3"
                :key="n"
              >
                <v-card>
                  <v-card-text>
                    {{ text }}
                  </v-card-text>
                </v-card>
              </v-tab-item>
            </v-tabs-items>
          </div>
        </td>
        
        <td v-else-if="props.item.num == 5" colspan="2" class="px-2 py-3">
          <v-tabs
            centered
            color="cyan"
            dark
            icons-and-text
          >
            <v-tabs-slider color="yellow"></v-tabs-slider>

            <v-tab href="#tab-1">
              Recents
              <v-icon>phone</v-icon>
            </v-tab>

            <v-tab href="#tab-2">
              Favorites
              <v-icon>favorite</v-icon>
            </v-tab>

            <v-tab href="#tab-3">
              Nearby
              <v-icon>account_box</v-icon>
            </v-tab>

            <v-tab-item
              v-for="i in 3"
              :id="'tab-' + i"
              :key="i"
            >
              <v-card flat>
                <v-card-text>{{ text }}</v-card-text>
              </v-card>
            </v-tab-item>
          </v-tabs>  
        </td>

        <td v-else-if="props.item.num == 6" colspan="2" class="px-2 py-3">
          <div>
            <v-toolbar color="cyan" dark tabs>
              <v-toolbar-side-icon></v-toolbar-side-icon>

              <v-toolbar-title>Page title</v-toolbar-title>

              <v-spacer></v-spacer>

              <v-btn icon>
                <v-icon>search</v-icon>
              </v-btn>

              <v-btn icon>
                <v-icon>more_vert</v-icon>
              </v-btn>

              <v-tabs
                slot="extension"
                v-model="tab6"
                color="cyan"
                align-with-title
              >
                <v-tabs-slider color="yellow"></v-tabs-slider>

                <v-tab v-for="item in items6" :key="item">
                  {{ item }}
                </v-tab>
              </v-tabs>
            </v-toolbar>

            <v-tabs-items v-model="tab6">
              <v-tab-item v-for="item in items6" :key="item">
                <v-card flat>
                  <v-card-text>{{ text }}</v-card-text>
                </v-card>
              </v-tab-item>
            </v-tabs-items>
          </div>
        </td>


        <td v-else-if="props.item.num == 7" colspan="2" class="px-2 py-3">
          <div>
            <v-toolbar
              color="cyan"
              dark
              tabs
            >
              <v-toolbar-side-icon></v-toolbar-side-icon>

              <v-toolbar-title>Page title</v-toolbar-title>

              <v-spacer></v-spacer>

              <v-btn icon>
                <v-icon>search</v-icon>
              </v-btn>

              <v-btn icon>
                <v-icon>more_vert</v-icon>
              </v-btn>

              <v-tabs
                slot="extension"
                v-model="tab7"
                color="cyan"
                grow
              >
                <v-tabs-slider color="yellow"></v-tabs-slider>

                <v-tab
                  v-for="item in items7"
                  :key="item"
                >
                  {{ item }}
                </v-tab>
              </v-tabs>
            </v-toolbar>

            <v-tabs-items v-model="tab7">
              <v-tab-item
                v-for="item in items7"
                :key="item"
              >
                <v-card flat>
                  <v-card-text>{{ text }}</v-card-text>
                </v-card>
              </v-tab-item>
            </v-tabs-items>
          </div>
        </td>

        <td v-else-if="props.item.num == 8" colspan="2" class="px-2 py-3">
          <div>
            <v-toolbar
              color="cyan"
              dark
              tabs
            >
              <v-toolbar-side-icon></v-toolbar-side-icon>

              <v-toolbar-title>Page title</v-toolbar-title>

              <v-spacer></v-spacer>

              <v-btn icon>
                <v-icon>search</v-icon>
              </v-btn>

              <v-btn icon>
                <v-icon>more_vert</v-icon>
              </v-btn>

              <v-tabs
                slot="extension"
                v-model="currentItem"
                color="transparent"
                fixed-tabs
                slider-color="yellow"
              >
                <v-tab
                  v-for="item in items8"
                  :href="'#tab-' + item"
                  :key="item"
                >
                  {{ item }}
                </v-tab>

                <v-menu
                  v-if="more8.length"
                  bottom
                  class="v-tabs__div"
                  left
                >
                  <a slot="activator" class="v-tabs__item">
                    more
                    <v-icon>arrow_drop_down</v-icon>
                  </a>

                  <v-list class="grey lighten-3">
                    <v-list-tile
                      v-for="item in more8"
                      :key="item"
                      @click="addItem(item)"
                    >
                      {{ item }}
                    </v-list-tile>
                  </v-list>
                </v-menu>
              </v-tabs>
            </v-toolbar>

            <v-tabs-items v-model="currentItem8">
              <v-tab-item
                v-for="item in items8.concat(more8)"
                :id="'tab-' + item"
                :key="item"
              >
                <v-card flat>
                  <v-card-text>
                    <h3>{{ item }}</h3>
                    {{ text }}
                  </v-card-text>
                </v-card>
              </v-tab-item>
            </v-tabs-items>
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
        tab_list: [
          {
            value: false,
            name: '固定タブ',
            text: "より大きい最小幅を設定して適応したタブ",
            url: "https://vuetifyjs.com/ja/components/tabs#example-fixed-tabs",
            num: 1,
          },  
          {
            value: false,
            name: '右揃え',
            text: "右揃えに並べたタブ",
            url: "https://vuetifyjs.com/ja/components/tabs#example-right",
            num: 2,
          },  
          {
            value: false,
            name: 'コンテンツ',
            text: "タブ内に他コンテンツ（ツールバーなど）を取り入れる",
            url: "https://vuetifyjs.com/ja/components/tabs#example-content",
            num: 3,
          },  
          {
            value: false,
            name: '検索機能',
            text: "タブ内に検索機能を取り入れる",
            url: "https://vuetifyjs.com/ja/components/tabs#example-search",
            num: 4,
          },  
          {
            value: false,
            name: 'アイコンとテキスト',
            text: "タブをアイコンとテキストで表示する",
            url: "https://vuetifyjs.com/ja/components/tabs#example-icons-and-text",
            num: 5
          },  
          {
            value: false,
            name: 'タブとツールバーの整列',
            text: "タブをツールバーのタイトルと並べる",
            url: "https://vuetifyjs.com/ja/components/tabs#example-align-with-title",
            num: 6
          },  
          {
            value: false,
            name: '最大幅での表示',
            text: "利用可能な領域を全て使ってタブを表示する",
            url: "https://vuetifyjs.com/ja/components/tabs#example-grow",
            num: 7
          },  
          {
            value: false,
            name: 'メニュー付き',
            text: "タブの中にメニューをつけて、追加のタブを表示する",
            url: "https://vuetifyjs.com/ja/components/tabs#example-overflow-to-menu",
            num: 8
          }, 
          {
            value: false,
            name: 'ページネーション',
            text: "タブ数が親コンテンツを越えた時、ページネーション表示になる",
            url: "https://vuetifyjs.com/ja/components/tabs#example-pagination",
            num: 9
          },  
          {
            value: false,
            name: 'ページネーションにアイコン付加',
            text: "ページネーションのページ移動のボタンをアイコンにする",
            url: "https://vuetifyjs.com/ja/components/tabs#example-icons",
            num: 10
          },  
        ],
        model3: 'tab-2',
        text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.',
        tabs4: null,
        tab6: null,
        items6: [
          'web', 'shopping', 'videos', 'images', 'news'
        ],
        tab7: null,
        items7: [
          'web', 'shopping', 'videos', 'images', 'news'
        ],
        currentItem8: 'tab-Web',
        items8: [
          'Web', 'Shopping', 'Videos', 'Images'
        ],
        more8: [
        'News', 'Maps', 'Books', 'Flights', 'Apps'
        ],
      }
    },
    methods: {
      addItem (item) {
        const removed = this.items8.splice(0, 1)
        this.items8.push(
          ...this.more8.splice(this.more8.indexOf(item), 1)
        )
        this.more8.push(...removed)
        this.$nextTick(() => { this.currentItem8 = 'tab-' + item })
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
