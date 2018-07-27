<template>
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


      <td v-if="props.item.num == 1" colspan="2">
        <div style="padding:10px 0px;">
          <v-expansion-panel
            v-model="panel1"
            expand
            style="border:solid 1px #ddd"
          >
            <v-expansion-panel-content
              v-for="(item, i) in 2"
              :key="i"
            >
              <div slot="header">Item</div>
              <v-card>
                <v-card-text class="grey lighten-3">test</v-card-text>
              </v-card>
            </v-expansion-panel-content>
          </v-expansion-panel>
        </div>
      </td>

      <td v-else-if="props.item.num == 2" colspan="2">
        <div style="padding:10px 0px;">
          <div class="d-flex justify-between align-center mb-3">
            <v-btn @click="all">all</v-btn>
            <v-btn @click="none">none</v-btn>
          </div>

          <v-expansion-panel
            v-model="panel2"
            expand
          >
            <v-expansion-panel-content
              v-for="(item,i) in items2"
              :key="i"
            >
              <div slot="header">Item</div>
              <v-card>
                <v-card-text>test</v-card-text>
              </v-card>
            </v-expansion-panel-content>
          </v-expansion-panel>
        </div>
      </td>


      <td v-else-if="props.item.num == 3" colspan="2">
        <div style="padding:10px 0px;">
          <v-expansion-panel
            v-model="panel_ft"
            :disabled="disabled"
            expand
            style="border:solid 1px #ddd;"
          >
            <v-expansion-panel-content disabled>
              <template slot="header">Disabled</template>
              <v-card>
                <v-card-text>
                  test
                </v-card-text>
              </v-card>
            </v-expansion-panel-content>
            <v-expansion-panel-content disabled>
              <template slot="header">Disabled</template>
              <v-card>
                <v-card-text>
                  開いた状態
                </v-card-text>
              </v-card>
            </v-expansion-panel-content>
          </v-expansion-panel>
        </div>
      </td>


      <td v-else-if="props.item.num == 4" colspan="2">
        <div style="padding:10px 0px;">
          <v-expansion-panel
            v-model="panel_ft"
            :readonly="readonly"
            expand
            style="border:solid 1px #ddd"
          >
            <v-expansion-panel-content readonly>
              <template slot="header">Readonly</template>
              <v-card>
                <v-card-text>
                  test
                </v-card-text>
              </v-card>
            </v-expansion-panel-content>
            <v-expansion-panel-content readonly>
              <template slot="header">Readonly</template>
              <v-card>
                <v-card-text>
                  開いた状態
                </v-card-text>
              </v-card>
            </v-expansion-panel-content>
          </v-expansion-panel>
        </div>  
      </td>


      <td v-else-if="props.item.num == 5" colspan="2">
        <div style="padding:10px 0px;">
          <v-expansion-panel popout>
            <v-expansion-panel-content
              v-for="(item,i) in 2"
              :key="i"
              style="border:solid 1px #ddd"
            >
              <div slot="header">Item</div>
              <v-card>
                <v-card-text>test</v-card-text>
              </v-card>
            </v-expansion-panel-content>
          </v-expansion-panel>
        </div>
      </td>

      <td v-else-if="props.item.num == 6" colspan="2">
        <div style="padding:10px 0px;">
          <v-expansion-panel inset>
            <v-expansion-panel-content
              v-for="(item,i) in 2"
              :key="i"
              style="border:solid 1px #ddd"
            >
              <div slot="header">Item</div>
              <v-card>
                <v-card-text>test</v-card-text>
              </v-card>
            </v-expansion-panel-content>
          </v-expansion-panel>
        </div>
      </td>

      <td v-else-if="props.item.num == 7" colspan="2">
        <div style="padding:10px 0px;">
          <v-expansion-panel focusable style="border:solid 1px #ddd">
            <v-expansion-panel-content
              v-for="(item,i) in 2"
              :key="i"
            >
              <div slot="header">Item</div>
              <v-card>
                <v-card-text class="grey lighten-3">test</v-card-text>
              </v-card>
            </v-expansion-panel-content>
          </v-expansion-panel>
        </div>
      </td>

    
    </template>
  </v-data-table>
</template>

<script>

  export default {
    data () {
      return {
        panel_list: [
          {
            value: false,
            name: '展開パネル',
            text: "閉じるまでは開いたままのパネル",
            url: "https://vuetifyjs.com/ja/components/expansion-panels#example-expand",
            num: 1,
          }, 
          {
            value: false,
            name: '外部コントロール',
            text: "パネル外から操作することでパネルを開閉する",
            url: "https://vuetifyjs.com/ja/components/expansion-panels#example-external",
            num: 2,
          }, 
          {
            value: false,
            name: '開閉無効',
            text: "開閉することのできないパネル",
            url: "https://vuetifyjs.com/ja/components/expansion-panels#example-disabled-and-readonly",
            num: 3,
          },
          {
            value: false,
            name: '読み取り専用',
            text: "読み取り専用のパネル",
            url: "https://vuetifyjs.com/ja/components/expansion-panels#example-disabled-and-readonly",
            num: 4,
          }, 
          {
            value: false,
            name: 'ポップアウト',
            text: "パネルが外に飛び出すように開く",
            url: "https://vuetifyjs.com/ja/components/expansion-panels#example-popout",
            num: 5,
          }, 
          {
            value: false,
            name: 'インセット',
            text: "パネルが中に引っ込むように開く",
            url: "https://vuetifyjs.com/ja/components/expansion-panels#example-popout",
            num: 6,
          }, 
          {
            value: false,
            name: 'フォーカス',
            text: "パネルを開いた際に、目立つようフォーカスする",
            url: "https://vuetifyjs.com/ja/components/expansion-panels#example-focusable",
            num: 7,
          }, 
        ],
        panel_ft: [false,true],
        panel1: [false, false],
        panel2: [],
        items2: 2,
        panel3: [true, true, false],
        disabled: false,
        readonly: false
      }
    },
    methods: {
      // Create an array the length of our items
      // with all values as true
      all () {
        this.panel2 = [...Array(this.items2).keys()].map(_ => true)
      },
      // Reset the panel
      none () {
        this.panel2 = []
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
