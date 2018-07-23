<template>
  <v-container fluid grid-list-md>
    <v-layout row wrap>

      <v-flex xs12 class="py-2">
        <h2>Vuetifyの基本構造</h2>   
        <v-divider></v-divider>
      </v-flex>

      <v-flex xs12>
        <v-card>
          <v-card-text>
            <div>
              まずはVuetifyにおける基本的な構造についてまとめる
            </div>
          </v-card-text>
        </v-card>   
      </v-flex>

      <v-flex xs12>
        <v-data-table
          :headers="headers"
          :items="contents"
          hide-actions
          class="elevation-1"
        >
          <template slot="items" slot-scope="props">
            <td>{{ props.item.name }}</td>
            <td>{{ props.item.text }}</td>
          </template>
        </v-data-table>
      </v-flex>

      <v-flex xs12 sm6>
        <v-card height="330px">
          <v-card-title primary-title>
              タグの入れ子関係
          </v-card-title>
          <v-card-text>
              &lt;v-app&gt;<br>
              □□&lt;v-navigation-drawer app&gt;&lt;/v-navigation-drawer&gt;<br>
              □□&lt;v-toolbar app&gt;&lt;/v-toolbar&gt;<br>
              □□&lt;v-content&gt;<br>
              □□□□&lt;v-container fluid&gt;<br>
              □□□□□□&lt;router-view&gt;&lt;/router-view&gt;<br>
              □□□□&lt;/v-container&gt;<br>
              □□&lt;/v-content&gt;<br>
              □□&lt;v-footer app&gt;&lt;/v-footer&gt;<br>
              &lt;/v-app&gt;<br>
          </v-card-text>
        </v-card>   
      </v-flex>

      <v-flex xs12 sm6>
        <v-card height="330px">
          <v-card-title primary-title>
              タグの入れ子関係（pug）
          </v-card-title>
          <v-card-text>
              v-app<br>
              □□v-navigation-drawer(app)<br>
              □□v-toolbar(app)<br>
              □□v-content<br>
              □□□□v-container(fluid)<br>
              □□□□□□router-view<br>
              □□v-footer(app)<br>
          </v-card-text>
        </v-card>   
      </v-flex>

      <v-flex xs12 class="py-2">
        <h2>グリッドシステム</h2>   
        <v-divider></v-divider>
      </v-flex>

      <v-flex xs12>
        <v-card>
          <v-card-text>
            <div>
              グリッドシステムによって、画面幅が変わってもそれに対応したレイアウトに整えてくれる。<br>
              Vuetifyでは、12ポイントのグリッドによって幅が構成されている。グリッド数(幅)は、「v-flex」のオプションで設定可能。<br>
              オプションについては、以下の記事がわかりやすい。<br>
              <a href="https://qiita.com/nulltemp/items/07c6998a4ad8927a9b54" target="_blank">
                Vuetifyのグリッドシステムの属性について
              </a>
            </div>
          </v-card-text>
        </v-card>   
      </v-flex>

      <v-flex xs12>
        <v-data-table
          :headers="headers"
          :items="contents2"
          hide-actions
          class="elevation-1"
        >
          <template slot="items" slot-scope="props">
            <td>{{ props.item.name }}</td>
            <td>{{ props.item.text }}</td>
          </template>
        </v-data-table>
      </v-flex>

      <v-flex xs12 sm6>
        <v-card height="230px">
          <v-card-title primary-title>
              タグの入れ子関係
          </v-card-title>
          <v-card-text>
              &lt;v-container fluid&gt;<br>
              □□&lt;v-layout&gt;<br>
              □□□□&lt;v-flex&gt;&lt;/v-flex&gt;<br>
              □□&lt;/v-layout&gt;<br>
              &lt;/v-container&gt;<br>
          </v-card-text>
        </v-card>   
      </v-flex>

      <v-flex xs12 sm6>
        <v-card height="230px">
          <v-card-title primary-title>
              タグの入れ子関係（pug）
          </v-card-title>
          <v-card-text>
              v-container(fluid)<br>
              □□v-layout<br>
              □□□□v-flex<br>
          </v-card-text>
        </v-card>   
      </v-flex>

      <v-flex xs12>
        <v-card>
          <GridSystem/>
        </v-card>
      </v-flex>

      <v-flex xs12 class="py-2">
        <h2>カード | v-card</h2>   
        <v-divider></v-divider>
      </v-flex>

      <v-flex xs12>
        <v-card>
          <v-card-text>
            <div>
              v-cardは、データのまとまりを入れる。汎用性が高い
            </div>
          </v-card-text>
        </v-card>   
      </v-flex>

      <v-flex xs12>
        <v-data-table
          :headers="headers"
          :items="contents3"
          hide-actions
          class="elevation-1"
        >
          <template slot="items" slot-scope="props">
            <td>{{ props.item.name }}</td>
            <td>{{ props.item.text }}</td>
          </template>
        </v-data-table>
      </v-flex>

      <v-flex xs12 sm6>
        <v-card height="430px">
          <v-card-media
            src="https://cdn.vuetifyjs.com/images/cards/sunshine.jpg" 
            height="200px"
          >
          </v-card-media>
          <v-card-title primary-title>
              タイトル：v-card-title
          </v-card-title>
          <v-card-text>
              本文：v-card-text<br>
              ※画像は以下のURLからお借りしました。<br>
              https://cdn.vuetifyjs.com/images/cards/sunshine.jpg
          </v-card-text>
          <v-card-actions>
            <v-btn color="blue lighten-4">v-card-actions</v-btn>
          </v-card-actions>
        </v-card>   
      </v-flex>

      <v-flex xs12 sm6>
        <v-card height="430px">
          <v-card-title primary-title>
              ソースコード（pug）
          </v-card-title>
          <v-card-text>
            v-flex(xs12 sm6)<br>
            □□v-card(height="400px")<br>
            □□□□v-card-media(src="URL" height="200px")<br>
            □□□□v-card-title タイトル：v-card-title<br>
            □□□□v-card-text 本文：v-card-text<br>
            □□□□v-card-actions<br>
            □□□□□□v-btn(color="blue lighten-4")<br>
          </v-card-text>
        </v-card>   
      </v-flex>

    </v-layout>
  </v-container>
</template>

<script>
  import GridSystem from './gridsystem'

  export default {
    components: {
      GridSystem,
    },
    data () {
      return {
        headers: [
          {
            text: 'v-〇〇',
            align: 'left',
            sortable: false,
            value: 'name'
          },
          { text: 'text', value: 'text' },
        ],
        contents: [
          {
            value: false,
            name: 'v-app',
            text: "Vuetifyのアプリケーションをうまく作動するためには必要。一番外枠になる。"
                  + "もしうまくVuetifyが動かない場合、これを入れ忘れている可能性があるかも"
          },
          {
            value: false,
            name: 'v-navigation-drawer',
            text: "いわゆるサイドメニュー。設定を変更していなければ、画面サイズが大きい時に左に出る"
          },
          {
            value: false,
            name: 'v-toolbar',
            text: "いわゆるヘッダーメニュー。上に出るやつ"
          },
          {
            value: false,
            name: 'v-content',
            text: "アプリケーションのコンテンツの主要部分"
          },
          {
            value: false,
            name: 'v-footer',
            text: "いわゆるフッター部分"
          },
        ],
        contents2: [
          {
            value: false,
            name: 'v-container',
            text: "v-layoutを囲む部分"
          },
          {
            value: false,
            name: 'v-layout',
            text: "v-flexの要素をひとかたまりにまとめている"
          },
          {
            value: false,
            name: 'v-flex',
            text: "一つの要素のまとまり。オプションで、画面の大きさに合わせた幅設定が可能"
          },
        ],
        contents3: [
          {
            value: false,
            name: 'v-card-media',
            text: "画像などを入れる場所"
          },
          {
            value: false,
            name: 'v-card-title',
            text: "タイトルを入れる場所"
          },
          {
            value: false,
            name: 'v-card-text',
            text: "テキストを入れる場所"
          },
          {
            value: false,
            name: 'v-card-actions',
            text: "ボタンなど、アクションのあるコンポーネントを入れる場所"
          },
        ]
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
</style>