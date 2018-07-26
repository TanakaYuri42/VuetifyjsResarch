<template>
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


      <td v-if="props.item.num == 1" colspan="2">
        <v-chip color="red" text-color="white">Colored</v-chip>
        <v-chip color="green" text-color="white">Chip</v-chip>
      </td>

      <td v-else-if="props.item.num == 2" colspan="2">
        <v-chip color="indigo" text-color="white">
          <v-avatar><v-icon>account_circle</v-icon></v-avatar>
          Icon
        </v-chip>
        <v-chip color="orange" text-color="white">
          Chip<v-icon right>star</v-icon>
        </v-chip>
      </td>

      <td v-else-if="props.item.num == 3" colspan="2">
        <v-chip outline color="primary">Outline</v-chip>
        <v-chip outline color="red"><v-icon left>build</v-icon>Chip</v-chip>  
      </td>

      <td v-else-if="props.item.num == 4" colspan="2">
        <v-chip label>Label</v-chip>
        <v-chip label color="pink" text-color="white">
          <v-icon left>label</v-icon>Tags
        </v-chip>
      </td>

      <td v-else-if="props.item.num == 5" colspan="2">
        <v-btn
          v-if="!chip1 && !chip2"
          color="primary"
          dark
          @click="chip1 = true, chip2 = true"
        >
          Reset Chips
        </v-btn>
        <v-chip
          v-model="chip1"
          close
        >Closable</v-chip>
        <v-chip
          v-model="chip2"
          close
          color="orange"
          label
          outline
        >Chip</v-chip>
      </td>

      <td v-else-if="props.item.num == 6" colspan="2">
        <v-combobox
          v-model="chips"
          :items="items"
          label="select and chip"
          chips
          clearable
          solo
          multiple
        >
          <template slot="selection" slot-scope="data">
            <v-chip
              :selected="data.selected"
              close
              @input="remove(data.item)"
            >
              <strong>{{ data.item }}</strong>&nbsp;
              <span>(interest)</span>
            </v-chip>
          </template>
        </v-combobox>
      </td>

      <td v-else-if="props.item.num == 7" colspan="2">
        <div class="text-xs-center d-flex align-center">
          <v-tooltip left>
            <v-btn
              slot="activator"
              color="primary"
              dark
            >
              Button
            </v-btn>
            <span>Tooltip</span>
          </v-tooltip>
          <v-tooltip bottom>
            <v-icon
              slot="activator"
              color="primary"
              dark
            >home</v-icon>
            <span>Tooltip</span>
          </v-tooltip>

          <v-tooltip right>
            <span slot="activator">This text has a tooltip</span>
            <span>Tooltip</span>
          </v-tooltip>
        </div>
      </td>
    
    </template>
  </v-data-table>
</template>

<script>

  export default {
    data () {
      return {
        chip_list: [
          {
            value: false,
            name: '色の設定',
            text: "チップに色をつける",
            url: "https://vuetifyjs.com/ja/components/chips#example-colored",
            num: 1,
          },  
          {
            value: false,
            name: 'アイコンの設定',
            text: "チップにアイコンをつける",
            url: "https://vuetifyjs.com/ja/components/chips#example-icon",
            num: 2,
          },
          {
            value: false,
            name: 'アウトラインチップ',
            text: "テキストの色を境界線として表示したチップ",
            url: "https://vuetifyjs.com/ja/components/chips#example-outline",
            num: 3,
          },  
          {
            value: false,
            name: 'ラベル',
            text: "ラベルのチップ。四角い",
            url: "https://vuetifyjs.com/ja/components/chips#example-label",
            num: 4,
          },
          {
            value: false,
            name: '閉じるボタン付きチップ',
            text: "チップに閉じるボタンをつける",
            url: "https://vuetifyjs.com/ja/components/chips#example-closable",
            num: 5,
          }, 
          {
            value: false,
            name: 'セレクトとの組み合わせ',
            text: "選択された項目の表示にチップを使う",
            url: "https://vuetifyjs.com/ja/components/chips#example-in-selects",
            num: 6,
          }, 
          {
            value: false,
            name: 'ツールチップ',
            text: "要素にホバーやクリックすることでチップを表示する",
            url: "https://vuetifyjs.com/ja/components/tooltips",
            num: 7,
          },   
        ],
        chip1: true,
        chip2: true,
        chips: ['1', '2'],
        items: ['A', 'B'],
      }
    },
    methods: {
      remove (item) {
        this.chips.splice(this.chips.indexOf(item), 1)
        this.chips = [...this.chips]
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
