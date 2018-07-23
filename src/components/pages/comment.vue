<template>
  <v-container fluid grid-list-md>
    <v-layout row wrap>

      <v-flex xs12 sm12 class="py-2">
        <h2>Vuetifyの基本構造</h2>   
        <v-divider></v-divider>
      </v-flex>

      <v-flex xs12>
        <v-card>
          <v-card-title primary-title>
            <div>
              まずはVuetifyにおける基本的な構造についてまとめる。
              「fluid」などオプションについては、以下の記事がわかりやすい。<br>
              <a href="https://qiita.com/nulltemp/items/07c6998a4ad8927a9b54" target="_blank">
                Vuetifyのグリッドシステムの属性について
              </a>
            </div>
          </v-card-title>
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
              &nbsp;&nbsp;&lt;v-navigation-drawer app&gt;&lt;/v-navigation-drawer&gt;<br>
              &nbsp;&nbsp;&lt;v-toolbar app&gt;&lt;/v-toolbar&gt;<br>
              &nbsp;&nbsp;&lt;v-content&gt;<br>
              &nbsp;&nbsp;&nbsp;&nbsp;&lt;v-container fluid&gt;<br>
              &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;router-view&gt;&lt;/router-view&gt;<br>
              &nbsp;&nbsp;&nbsp;&nbsp;&lt;/v-container&gt;<br>
              &nbsp;&nbsp;&lt;/v-content&gt;<br>
              &nbsp;&nbsp;&lt;v-footer app&gt;&lt;/v-footer&gt;<br>
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
              &nbsp;&nbsp;v-navigation-drawer(app)<br>
              &nbsp;&nbsp;v-toolbar(app)<br>
              &nbsp;&nbsp;v-content<br>
              &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;v-container(fluid)<br>
              &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;router-view<br>
              &nbsp;&nbsp;v-footer(app)<br>
          </v-card-text>
        </v-card>   
      </v-flex>

      <v-flex xs12 sm12 class="py-2">
        <h2>グリッドシステム</h2>   
        <v-divider></v-divider>
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
              &nbsp;&nbsp;&nbsp;&lt;v-layout&gt;<br>
              &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;v-flex&gt;&lt;/v-flex&gt;<br>
              &nbsp;&nbsp;&nbsp;&lt;/v-layout&gt;<br>
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
              &nbsp;&nbsp;&nbsp;&nbsp;v-layout<br>
              &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;v-flex<br>
          </v-card-text>
        </v-card>   
      </v-flex>

      <v-flex xs12 sm12 class="py-2">
        <h2>カード | v-card</h2>   
        <v-divider></v-divider>
      </v-flex>

      <v-flex xs12>
        <v-card>
          <v-card-title primary-title>
            <div>
              v-cardは、データのまとまり。汎用性が高い。
            </div>
          </v-card-title>
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
        <v-card height="230px">
          <v-card-title primary-title>
              見本のカード
          </v-card-title>
          <v-card-media src="../../../assets/1.png"></v-card-media>
          <v-card-text>
              このようにv-cardは使えます
          </v-card-text>
        </v-card>   
      </v-flex>

    </v-layout>
  </v-container>
</template>

<script>
  export default {
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
            text: "いわゆるサイドメニュー。設定を変更していなければ、画面幅が大きい時に左に出る"
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
            text: ""
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
