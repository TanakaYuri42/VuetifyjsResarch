<template>
  <v-container grid-list-md text-xs-center>
    <v-layout row wrap>

      <v-flex xs12>
        <v-card dark color="primary">
          <v-card-text class="px-0">&lt;v-flex xs12&gt;</v-card-text>
        </v-card>
      </v-flex>

      <v-flex v-for="i in 2" :key="`6${i}`" xs6>
        <v-card dark color="secondary">
          <v-card-text class="px-0">&lt;v-flex xs6&gt;</v-card-text>
        </v-card>
      </v-flex>

      <v-flex v-for="i in 3" :key="`4${i}`" xs4>
        <v-card dark color="purple">
          <v-card-text class="px-0">&lt;v-flex xs4&gt;</v-card-text>
        </v-card>
      </v-flex>

      <v-flex v-for="i in 2" :key="`6${i}`" xs12 md6>
        <v-card dark  color="green">
          <v-card-text class="px-0">&lt;v-flex xs12 md6&gt;</v-card-text>
        </v-card>
      </v-flex>

      <v-flex xs12>
        <v-card text-xs-left>
          <v-card-text class="text-left">
            <div>
              上のように、v-flexのオプションに「画面サイズ+グリッド数」で設定する。<br>
              この画面サイズについては、公式サイトの
              <a href="https://vuetifyjs.com/ja/layout/breakpoints" target="_blank">Breakpoints</a>
              参照。
            </div>
          </v-card-text>
        </v-card>   
      </v-flex>

      <v-flex xs12 class="text-left">
        <v-data-table
          :headers="headers"
          :items="gridsizeList"
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
  props: {
    msg: String
  },
  data () {
    return {
      headers: [
        {
          text: '画面サイズ',
          align: 'left',
          sortable: false,
          value: 'name'
        },
        { text: 'text', value: 'text' },
      ],
      gridsizeList: [
        {
          value: false,
          name: 'xs',
          text: "Extra Small。600px未満の画面サイズで、スマホがこのくらい"
        },
        {
          value: false,
          name: 'sm',
          text: "Small。600px~960pxの画面サイズで、一部スマホやタブレットがこのくらい"
        },
        {
          value: false,
          name: 'md',
          text: "Medium。960px~1264pxの画面サイズで、パソコンがこのくらい"
        },
        {
          value: false,
          name: 'lg',
          text: "Large。1264px~1904pxの画面サイズで、大画面のパソコンがこのくらい"
        },
        {
          value: false,
          name: 'xl',
          text: "Extra large。1904pxよりも大きい画面サイズで、大画面のテレビがこのくらい"
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
.text-left{
  text-align:left;
}
</style>
