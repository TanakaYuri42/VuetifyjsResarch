<template>
  <v-container fluid grid-list-md>
    <v-layout row wrap>

      <v-flex xs12 class="py-2">
        <h2>componentまとめ</h2>   
        <v-divider></v-divider>
      </v-flex>

      <v-flex xs12>
        <v-data-table
          :headers="headers"
          :items="all_list"
          hide-actions
          class="elevation-1"
        >
          <template slot="items" slot-scope="props">
            <td>{{ props.item.name }}</td>
            <td>{{ props.item.text }}</td>
          </template>
        </v-data-table>
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
        all_list: [
          {
            value: false,
            name: 'v-alert',
            text: "アラート表示。アイコンや閉じるボタンの挿入も可能"
          },
          {
            value: false,
            name: 'v-avatar',
            text: "画像のサイズや角丸の制御をユーザー側で行える"
          },
          {
            value: false,
            name: 'v-badge',
            text: "あらゆる要素にバッジをつけられる"
          },
          {
            value: false,
            name: 'v-bottom-nav',
            text: "サイドバーの代わりに使用できる下部メニュー"
          },
          {
            value: false,
            name: 'v-bottom-sheet',
            text: "スクリーン下部からスライドを出す"
          },
          {
            value: false,
            name: 'v-breadcrumbs',
            text: "パンくずリスト"
          },
          {
            value: false,
            name: 'v-btn',
            text: "ボタン"
          },
          {
            value: false,
            name: 'v-carousel',
            text: "時間経過で入れ替わる画像のスライドショー"
          },
          {
            value: false,
            name: 'v-chip',
            text: "閉じるボタンなど、小さな情報を付加する。チップ"
          },
          {
            value: false,
            name: 'v-data-iterator',
            text: "データの表示を制御する。ソート機能やページネーションなどの機能あり"
          },
          {
            value: false,
            name: 'v-data-table',
            text: "表形式のデータ。htmlでいうtableタグのようなもの"
          },
          {
            value: false,
            name: 'v-dialog',
            text: "ダイアログ機能"
          },
          {
            value: false,
            name: 'v-divider',
            text: "リスト中の要素の区切り線"
          },
          {
            value: false,
            name: 'v-expansion-panel',
            text: "パネル。クリックなどで情報を開いたり閉じたりできる"
          },
        ],
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
