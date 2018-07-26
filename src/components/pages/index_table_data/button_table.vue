<template>
  <v-data-table
    :headers="headers"
    :items="button_list"
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
        <td v-if="props.item.num == 13" colspan="2">{{ props.item.text }}</td>
        <td v-else>{{ props.item.text }}</td>
        

        <td v-if="props.item.num == 1">
          <v-btn flat>Flat</v-btn>
        </td>
        <td v-else-if="props.item.num == 2">
          <v-btn>Raised</v-btn>
        </td>
        <td v-else-if="props.item.num == 3">
          <v-btn depressed>Depressed</v-btn>
        </td>
        <td v-else-if="props.item.num == 4">
          <v-overflow-btn
            :items="dropdown_font"
            label="Dropdown"
            target="#dropdown-example"
          ></v-overflow-btn>
        </td>
        <td v-else-if="props.item.num == 5">
          <v-btn-toggle v-model="toggle_exclusive">
            <v-btn flat><v-icon>format_align_left</v-icon></v-btn>
            <v-btn flat><v-icon>format_align_center</v-icon></v-btn>
            <v-btn flat><v-icon>format_align_right</v-icon></v-btn>
            <v-btn flat><v-icon>format_align_justify</v-icon></v-btn>
          </v-btn-toggle>
          <v-divider></v-divider>
          <v-btn-toggle v-model="toggle_multiple" multiple>
            <v-btn flat><v-icon>format_bold</v-icon></v-btn>
            <v-btn flat><v-icon>format_italic</v-icon></v-btn>
            <v-btn flat><v-icon>format_underlined</v-icon></v-btn>
            <v-btn flat><v-icon>format_color_fill</v-icon></v-btn>
          </v-btn-toggle>
        </td>
        <td v-else-if="props.item.num == 6">
          <v-btn flat icon color="pink"><v-icon>favorite</v-icon></v-btn>
          <v-btn flat icon color="green"><v-icon>cached</v-icon></v-btn>
          <v-btn flat icon color="deep-orange"><v-icon>thumb_up</v-icon></v-btn>
        </td>
        <td v-else-if="props.item.num == 7">
          <v-btn fab dark small color="pink"></v-btn>
          <v-btn fab dark small color="indigo"><v-icon dark>add</v-icon></v-btn>
        </td>
        <td v-else-if="props.item.num == 8">
          <v-btn
            :loading="loading"
            :disabled="loading"
            color="secondary"
            @click.native="loader = 'loading'"
          >
            Loading
          </v-btn>
        </td>
        <td v-else-if="props.item.num == 9">
          <v-btn small color="primary" dark>S</v-btn>
          <v-btn color="warning" dark>N</v-btn>
          <v-btn color="error" dark large>L</v-btn>
        </td>
        <td v-else-if="props.item.num == 10">
          <v-btn outline color="indigo">Outline</v-btn>
          <v-btn outline fab small color="teal"><v-icon>list</v-icon></v-btn>
        </td>
        <td v-else-if="props.item.num == 11">
          <v-btn round color="primary" dark>Rounded</v-btn>
        </td>
        <td v-else-if="props.item.num == 12">
          <v-btn block color="secondary" dark>Block</v-btn>
        </td>
        <td v-else-if="props.item.num == 14" position: relative>
          <v-btn
                relative
                dark
                fab
                top
                right
                color="pink"
                style = "margin:-10px 0 20px 30px"
              >
                <v-icon>add</v-icon>
            </v-btn>
        </td>
      </tr>


      <tr v-if="props.item.num == 13">
        <td colspan="3" style="padding:10px 0;">
          <v-toolbar dense>
            <v-overflow-btn
              :items="dropdown_font"
              label="Select font"
              hide-details
            ></v-overflow-btn>

            <v-divider vertical></v-divider>

            <v-overflow-btn
              :items="dropdown_edit"
              editable
              label="Select size"
              hide-details
              overflow
            ></v-overflow-btn>

            <v-divider
              class="mr-2"
              vertical
            ></v-divider>

            <v-btn-toggle
              v-model="toggle_multiple"
              class="transparent"
              multiple
            >
              <v-btn :value="1" flat>
                <v-icon>format_bold</v-icon>
              </v-btn>

              <v-btn :value="2" flat>
                <v-icon>format_italic</v-icon>
              </v-btn>

              <v-btn :value="3" flat>
                <v-icon>format_underlined</v-icon>
              </v-btn>

              <v-btn :value="4" flat>
                <v-icon>format_color_fill</v-icon>
              </v-btn>
            </v-btn-toggle>

            <v-divider
              class="mx-2"
              vertical
            ></v-divider>

            <v-btn-toggle
              v-model="toggle_exclusive"
              class="transparent"
            >
              <v-btn :value="1" flat>
                <v-icon>format_align_left</v-icon>
              </v-btn>

              <v-btn :value="2" flat>
                <v-icon>format_align_center</v-icon>
              </v-btn>

              <v-btn :value="3" flat>
                <v-icon>format_align_right</v-icon>
              </v-btn>

              <v-btn :value="4" flat>
                <v-icon>format_align_justify</v-icon>
              </v-btn>
            </v-btn-toggle>
          </v-toolbar>
        </td>
      </tr>
      
    </template>
  </v-data-table>
</template>

<script>

  export default {
    data () {
      return {
      button_list: [
          {
            value: false,
            num: 1,
            name: "フラットボタン",
            text: "影と背景色を持たないボタン。カーソルを合わせると背景が浮かび上がる",
            url: "https://vuetifyjs.com/ja/components/buttons#example-flat",
            graphic: "<v-btn flat small>Normal</v-btn>"
          },
          {
            value: false,
            num: 2,
            name: 'レイズドボタン',
            text: "クリックした時に影が広がるボタン",
            url:"https://vuetifyjs.com/ja/components/buttons#example-raised",
            graphic: "<v-btn small>Normal</v-btn>"
          },
          {
            value: false,
            num: 3,
            name: 'ディプレスドボタン',
            text: "背景色は持つが、影は持たないボタン",
            url: "https://vuetifyjs.com/ja/components/buttons#example-depressed",
          },
          {
            value: false,
            num: 4,
            name: 'ドロップダウンボタン',
            text: "クリックするとリストを表示できるボタン",
            url: "https://vuetifyjs.com/ja/components/buttons#example-dropdown",
          },
          {
            value: false,
            num: 5,
            name: 'トグルボタン',
            text: "ラジオボタンやチェックボックスの作成",
            url:"https://vuetifyjs.com/ja/components/buttons#example-toggle"
          },
          {
            value: false,
            num: 6,
            name: 'アイコンのボタン化',
            text: "アイコンをボタンとして使用する",
            url: "https://vuetifyjs.com/ja/components/buttons#example-icon",
          },
          {
            value: false,
            num: 7,
            name: 'フローティングボタン',
            text: "丸いボタン",
            url: "https://vuetifyjs.com/ja/components/buttons#example-floating"
          },
          {
            value: false,
            num: 8,
            name: 'ローディング',
            text: "クリックすると、処理中であることを表示するボタン",
            url: "https://vuetifyjs.com/ja/components/buttons#example-loaders"
          },
          {
            value: false,
            num: 9,
            name: 'サイズ変更',
            text: "smallやlargeなど、ボタンのサイズを変更する",
            url: "https://vuetifyjs.com/ja/components/buttons#example-sizing"
          },
          {
            value: false,
            num: 10,
            name: 'アウトラインボタン',
            text: "現在適用されている色を境界線として表示したボタン",
            url: "https://vuetifyjs.com/ja/components/buttons#example-outline"
          },
          {
            value: false,
            num: 11,
            name: 'ラウンドボタン',
            text: "角が丸くなったボタン",
            url: "https://vuetifyjs.com/ja/components/buttons#example-round"
          },
          {
            value: false,
            num: 12,
            name: 'ブロックボタン',
            text: "可能な限り横に広がったボタン",
            url: "https://vuetifyjs.com/ja/components/buttons#example-block"
          },
          {
            value: false,
            num: 14,
            name: 'フローティングアクションボタン',
            text: "浮いているボタン。ユーザーにアクションを促すのによく使われる",
            url: "https://vuetifyjs.com/ja/components/floating-action-buttons"
          },
          {
            value: false,
            num: 13,
            name: 'ツールバーとの組み合わせ',
            text: "ツールバーにボタンを入れる",
            url: "https://vuetifyjs.com/ja/components/buttons#example-app-bar"
          },
        ],
        dropdown_font: [
          { text: 'Arial' },
          { text: 'Calibri' },
          { text: 'Courier' },
          { text: 'Verdana' }
        ],
        dropdown_edit: [
          { text: '100%' },
          { text: '75%' },
          { text: '50%' },
          { text: '25%' },
          { text: '0%' }
        ],
        toggle_none: null,
        toggle_one: 0,
        toggle_exclusive: 2,
        toggle_multiple: [0, 1, 2],
        loader: null,
        loading: false,
        loading2: false,
        loading3: false,
        loading4: false,
        hidden: false
      }
    },
    watch: {
      loader () {
        const l = this.loader
        this[l] = !this[l]

        setTimeout(() => (this[l] = false), 3000)

        this.loader = null
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
