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
        <td v-if="props.item.num == 1" colspan="2">

        </td>
        <td v-else-if="props.item.num == 2" colspan="2">
            
        </td>
        <td v-else-if="props.item.num == 3" colspan="2">
          
        </td>
        <td v-else-if="props.item.num == 4" colspan="2">
          
        </td>
        <td v-else-if="props.item.num == 5" colspan="2">
          
        </td>
        <td v-else-if="props.item.num == 6" colspan="2">
          
        </td>
        <td v-else-if="props.item.num == 7" colspan="2">

        </td>
        <td v-else-if="props.item.num == 8" colspan="2">
            
        </td>
        <td v-else-if="props.item.num == 9" colspan="2">
          
        </td>
        <td v-else-if="props.item.num == 10" colspan="2">
          
        </td>
        <td v-else-if="props.item.num == 11" colspan="2">
          
        </td>
        <td v-else-if="props.item.num == 12" colspan="2">
          
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
            url: "https://vuetifyjs.com/ja/components/toolbars#example-app-bar"
          },  
          {
            value: false,
            name: 'ボタンを使用したアプリケーションバー',
            text: "ボタンをアプリケーション項目として追加する",
            url: "https://vuetifyjs.com/ja/components/toolbars#example-app-bar-items"
          },  
          {
            value: false,
            name: '拡張機能付き',
            text: "拡張機能を追加したアプリケーションバー",
            url: "https://vuetifyjs.com/ja/components/toolbars#example-app-bar-extension"
          },  
          {
            value: false,
            name: '幅を階層化する',
            text: "ツールバーの幅を階層化する",
            url: "https://vuetifyjs.com/ja/components/toolbars#example-column-width-with-hierarchy"
          },
          {
            value: false,
            name: '柔軟なツールバー',
            text: "カード（v-card）を含めるなど、ツールバーを柔軟にカスタムする",
            url: "https://vuetifyjs.com/ja/components/toolbars#example-flexible-and-card"
          },  
          {
            value: false,
            name: '検索付きフローティングツールバー',
            text: "検索機能をつけて、参照するコンテンツ上にツールバーを設置する",
            url: "https://vuetifyjs.com/ja/components/toolbars#example-floating-with-search"
          },  
          {
            value: false,
            name: 'バリエーション',
            text: "テーマやヘルパークラスなど、バリエーションを設定する",
            url: "https://vuetifyjs.com/ja/components/toolbars#example-variations"
          },  
          {
            value: false,
            name: '主要なツールバー',
            text: "拡張領域に、要素を配置できるスロットを追加する",
            url: "https://vuetifyjs.com/ja/components/toolbars#example-prominent"
          },  
          {
            value: false,
            name: '高密度のツールバー',
            text: "高さを48pxに減らす",
            url: "https://vuetifyjs.com/ja/components/toolbars#example-dense"
          },  
          {
            value: false,
            name: 'スクロール',
            text: "スクロールする時に、ツールバーを画面から切り替える",
            url: "https://vuetifyjs.com/ja/components/toolbars#example-scrolling"
          },  
          {
            value: false,
            name: 'メニュー付きアプリケーションバー',
            text: "アプリケーションバーにメニューをつける",
            url: "https://vuetifyjs.com/ja/components/toolbars#example-app-bar-menu"
          }, 
          {
            value: false,
            name: 'システムバー',
            text: "システムバーを作成する",
            url: "https://vuetifyjs.com/ja/components/toolbars#example-system-bars-status-window"
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

table{
  border:solid 1px #ddd;
  width:100%;
}

td{
  border:solid 1px #ddd;
}
</style>
