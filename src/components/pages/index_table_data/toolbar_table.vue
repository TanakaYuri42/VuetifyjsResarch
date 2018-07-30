<template>
  <v-data-table
    :headers="headers"
    :items="toolbar_list"
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
        <td v-if="props.item.num == 1" colspan="2" class="pt-3 pb-3">
          <v-toolbar dark color="primary">
            <v-toolbar-side-icon></v-toolbar-side-icon>

            <v-toolbar-title class="white--text">Title</v-toolbar-title>

            <v-spacer></v-spacer>

            <v-btn icon>
              <v-icon>search</v-icon>
            </v-btn>

            <v-btn icon>
              <v-icon>apps</v-icon>
            </v-btn>

            <v-btn icon>
              <v-icon>refresh</v-icon>
            </v-btn>

            <v-btn icon>
              <v-icon>more_vert</v-icon>
            </v-btn>
          </v-toolbar>
        </td>


        <td v-else-if="props.item.num == 2" colspan="2" class="pt-3 pb-3">
          <v-toolbar>
            <v-spacer></v-spacer>
            <v-toolbar-items>
              <v-btn flat>Link One</v-btn>
              <v-btn flat>Link Two</v-btn>
              <v-btn flat>Link Three</v-btn>
            </v-toolbar-items>
          </v-toolbar>
        </td>


        <td v-else-if="props.item.num == 3" colspan="2" class="pt-3 pb-3">
          <v-toolbar
            color="primary"
            dark
            extended
          >
            <v-toolbar-side-icon></v-toolbar-side-icon>

            <v-toolbar-title slot="extension" class="white--text">Title</v-toolbar-title>

            <v-spacer></v-spacer>

            <v-btn icon>
              <v-icon>search</v-icon>
            </v-btn>

            <v-btn icon>
              <v-icon>apps</v-icon>
            </v-btn>

            <v-btn icon>
              <v-icon>refresh</v-icon>
            </v-btn>

            <v-btn icon>
              <v-icon>more_vert</v-icon>
            </v-btn>
          </v-toolbar>
        </td>


        <td v-else-if="props.item.num == 4" colspan="2" class="pt-3 pb-3">
          <v-card flat>
            <v-container fluid>
              <v-layout row child-flex wrap>
                <div>
                  <v-toolbar>
                    <v-btn icon class="hidden-xs-only">
                      <v-icon>arrow_back</v-icon>
                    </v-btn>

                    <v-toolbar-title>Title</v-toolbar-title>

                    <v-spacer></v-spacer>

                    <v-btn icon class="hidden-xs-only">
                      <v-icon>search</v-icon>
                    </v-btn>
                  </v-toolbar>
                </div>

                <div style="flex-basis: 20%">
                  <v-toolbar dark>
                    <v-spacer></v-spacer>

                    <v-btn icon>
                      <v-icon>reply</v-icon>
                    </v-btn>

                    <v-btn icon>
                      <v-icon>more_vert</v-icon>
                    </v-btn>
                  </v-toolbar>
                </div>
              </v-layout>
            </v-container>
          </v-card>
        </td>


        <td v-else-if="props.item.num == 5" colspan="2" class="pt-3 pb-3">
          <v-card flat>
            <v-toolbar
              color="primary"
              dark
              extended
              flat
            >
              <v-toolbar-side-icon></v-toolbar-side-icon>
            </v-toolbar>

            <v-layout row pb-2>
              <v-flex xs8 offset-xs2>
                <v-card class="card--flex-toolbar">
                  <v-toolbar card prominent>
                    <v-toolbar-title class="body-2 grey--text">Title</v-toolbar-title>

                    <v-spacer></v-spacer>

                    <v-btn icon>
                      <v-icon>search</v-icon>
                    </v-btn>

                    <v-btn icon>
                      <v-icon>apps</v-icon>
                    </v-btn>

                    <v-btn icon>
                      <v-icon>more_vert</v-icon>
                    </v-btn>
                  </v-toolbar>

                  <v-divider></v-divider>

                  <v-card-text style="height: 200px;"></v-card-text>
                </v-card>
              </v-flex>
            </v-layout>
          </v-card>
        </td>


        <td v-else-if="props.item.num == 6" colspan="2" class="pt-3 pb-3">
          <v-card
            class="pa-3"
            flat
            height="300px"
            img="https://cdn.vuetifyjs.com/images/toolbar/map.jpg"
          >
            <v-toolbar
              dense
              floating
            >
              <v-text-field
                hide-details
                prepend-icon="search"
                single-line
              ></v-text-field>

              <v-btn icon>
                <v-icon>my_location</v-icon>
              </v-btn>

              <v-btn icon>
                <v-icon>more_vert</v-icon>
              </v-btn>
            </v-toolbar>
          </v-card>
        </td>


        <td v-else-if="props.item.num == 7" colspan="2" class="pt-3 pb-3">
          <v-layout row wrap>
            <v-flex
              v-for="(bar, i) in bars"
              :key="i"
              xs12
              sm12
              md6
              class="my-1"
            >
              <v-toolbar :color="bar.class" :dark="bar.dark">
                <v-toolbar-side-icon></v-toolbar-side-icon>
                <v-toolbar-title>Title</v-toolbar-title>
                <v-spacer></v-spacer>
                <v-btn icon>
                  <v-icon>search</v-icon>
                </v-btn>
                <v-btn icon>
                  <v-icon>favorite</v-icon>
                </v-btn>
                <v-btn icon>
                  <v-icon>more_vert</v-icon>
                </v-btn>
              </v-toolbar>
            </v-flex>
          </v-layout>
        </td>


        <td v-else-if="props.item.num == 8" colspan="2" class="pt-3 pb-3">
          <v-card
            color="grey lighten-4"
            flat
            height="200px"
            tile
          >
            <v-toolbar prominent extended>
              <v-toolbar-side-icon></v-toolbar-side-icon>

              <v-toolbar-title>Title</v-toolbar-title>

              <v-spacer></v-spacer>

              <v-btn icon>
                <v-icon>search</v-icon>
              </v-btn>

              <v-btn icon>
                <v-icon>favorite</v-icon>
              </v-btn>

              <v-btn icon>
                <v-icon>more_vert</v-icon>
              </v-btn>
            </v-toolbar>
          </v-card>
        </td>


        <td v-else-if="props.item.num == 9" colspan="2" class="pt-3 pb-3">
          <v-card
            color="grey lighten-4"
            flat
            height="100px"
            tile
          >
            <v-toolbar dense>
              <v-toolbar-side-icon></v-toolbar-side-icon>

              <v-toolbar-title>Title</v-toolbar-title>

              <v-spacer></v-spacer>

              <v-btn icon>
                <v-icon>search</v-icon>
              </v-btn>

              <v-btn icon>
                <v-icon>favorite</v-icon>
              </v-btn>

              <v-btn icon>
                <v-icon>more_vert</v-icon>
              </v-btn>
            </v-toolbar>
          </v-card>
        </td>


        <td v-else-if="props.item.num == 10" colspan="2" class="pt-3 pb-3">
          <div
            class="hide-overflow"
            style="position: relative;"
          >
            <v-toolbar
              absolute
              color="teal lighten-3"
              dark
              scroll-off-screen
              scroll-target="#scrolling-techniques"
            >
              <v-toolbar-side-icon></v-toolbar-side-icon>

              <v-toolbar-title>Title</v-toolbar-title>

              <v-spacer></v-spacer>

              <v-btn icon>
                <v-icon>search</v-icon>
              </v-btn>

              <v-btn icon>
                <v-icon>favorite</v-icon>
              </v-btn>

              <v-btn icon>
                <v-icon>more_vert</v-icon>
              </v-btn>
            </v-toolbar>
            <div
              id="scrolling-techniques"
              class="scroll-y"
              style="max-height: 200px;"
            >
              <v-container style="height: 700px;"></v-container>
            </div>
          </div>
        </td>


        <td v-else-if="props.item.num == 11" colspan="2" class="pt-3 pb-3">
          <v-toolbar color="grey darken-1" dark>
            <v-toolbar-side-icon></v-toolbar-side-icon>

            <v-menu :nudge-width="100">
              <v-toolbar-title slot="activator">
                <span>All</span>
                <v-icon dark>arrow_drop_down</v-icon>
              </v-toolbar-title>

              <v-list>
                <v-list-tile
                  v-for="item in items11"
                  :key="item"
                >
                  <v-list-tile-title v-text="item"></v-list-tile-title>
                </v-list-tile>
              </v-list>
            </v-menu>

            <v-spacer></v-spacer>

            <v-btn icon>
              <v-icon>search</v-icon>
            </v-btn>

            <v-btn icon>
              <v-icon>favorite</v-icon>
            </v-btn>

            <v-btn icon>
              <v-icon>more_vert</v-icon>
            </v-btn>
          </v-toolbar>
        </td>


        <td v-else-if="props.item.num == 12" colspan="2" class="pt-3 pb-3">
          <div>
            <v-card img="https://cdn.vuetifyjs.com/images/home/vuetify_layout1.svg" height="200px">
              <v-system-bar status color="primary">
                <v-spacer></v-spacer>
                <v-icon>network_wifi</v-icon>
                <v-icon>signal_cellular_null</v-icon>
                <v-icon>battery_full</v-icon>
                <span>12:30</span>
              </v-system-bar>
            </v-card>
            <v-divider class="my-2"></v-divider>
            <v-system-bar window dark>
              <v-spacer></v-spacer>
              <v-icon>remove</v-icon>
              <v-icon>check_box_outline_blank</v-icon>
              <v-icon>close</v-icon>
            </v-system-bar>
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
        toolbar_list: [
          {
            value: false,
            name: 'アプリケーションバー',
            text: "アプリケーションの主要なツールバー。アイコンやメニューの追加可能",
            url: "https://vuetifyjs.com/ja/components/toolbars#example-app-bar",
            num: 1
          },  
          {
            value: false,
            name: 'ボタンを使用したアプリケーションバー',
            text: "ボタンをアプリケーション項目として追加する",
            url: "https://vuetifyjs.com/ja/components/toolbars#example-app-bar-items",
            num: 2,
          },  
          {
            value: false,
            name: '拡張機能付き',
            text: "拡張機能を追加したアプリケーションバー",
            url: "https://vuetifyjs.com/ja/components/toolbars#example-app-bar-extension",
            num: 3
          },  
          {
            value: false,
            name: '幅を階層化する',
            text: "ツールバーの幅を階層化する",
            url: "https://vuetifyjs.com/ja/components/toolbars#example-column-width-with-hierarchy",
            num: 4
          },
          {
            value: false,
            name: '柔軟なツールバー',
            text: "カード（v-card）を含めるなど、ツールバーを柔軟にカスタムする",
            url: "https://vuetifyjs.com/ja/components/toolbars#example-flexible-and-card",
            num: 5,
          },  
          {
            value: false,
            name: '検索付きフローティングツールバー',
            text: "検索機能をつけて、参照するコンテンツ上にツールバーを設置する",
            url: "https://vuetifyjs.com/ja/components/toolbars#example-floating-with-search",
            num: 6
          },  
          {
            value: false,
            name: 'バリエーション',
            text: "テーマやヘルパークラスなど、バリエーションを設定する",
            url: "https://vuetifyjs.com/ja/components/toolbars#example-variations",
            num: 7
          },  
          {
            value: false,
            name: '主要なツールバー',
            text: "拡張領域に、要素を配置できるスロットを追加する",
            url: "https://vuetifyjs.com/ja/components/toolbars#example-prominent",
            num: 8
          },  
          {
            value: false,
            name: '高密度のツールバー',
            text: "高さを48pxに減らす",
            url: "https://vuetifyjs.com/ja/components/toolbars#example-dense",
            num: 9,
          },  
          {
            value: false,
            name: 'スクロール',
            text: "スクロールする時に、ツールバーを画面から切り替える",
            url: "https://vuetifyjs.com/ja/components/toolbars#example-scrolling",
            num: 10,
          },  
          {
            value: false,
            name: 'メニュー付きアプリケーションバー',
            text: "アプリケーションバーにメニューをつける",
            url: "https://vuetifyjs.com/ja/components/toolbars#example-app-bar-menu",
            num: 11
          }, 
          {
            value: false,
            name: 'システムバー',
            text: "システムバーを作成する",
            url: "https://vuetifyjs.com/ja/components/toolbars#example-system-bars-status-window",
            num: 12
          },  
        ],
        bars: [
          { 'class': '' },
          { 'class': '', dark: true },
          { 'class': 'primary', dark: true },
          { 'class': 'elevation-0' }
        ],
        items11: [
          'All', 'Family', 'Friends', 'Coworkers'
        ]
      }
    }
  }
</script>


<style scoped>
.card--flex-toolbar {
    margin-top: -64px;
    border:solid 1px #ddd
}
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
