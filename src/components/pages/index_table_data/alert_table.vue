<template>
  <v-data-table
    :headers="headers"
    :items="alert_list"
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

      <tr class="tr-bottom">    
        <td v-if="props.item.num == 1" colspan="2">
          <v-alert
            v-model="alert"
            dismissible
            type="success"
            class="mt-3 mb-3"
          >
            This is a success alert that is closable.
          </v-alert>
          <div class="text-xs-center">
            <v-btn
              v-if="!alert"
              color="primary"
              dark
              @click="alert = true"
            >
              Reset
            </v-btn>
          </div>
        </td>

        <td v-else-if="props.item.num == 2" colspan="2">
          <v-alert
            :value="true"
            color="success"
            icon="new_releases"
            class="mt-3"
          >
            This is a success alert with a custom icon.
          </v-alert>

          <v-alert
            :value="true"
            color="error"
            class="mb-3"
          >
            This is an error alert with no icon.
          </v-alert>
        </td>

        <td v-else-if="props.item.num == 3" colspan="2">
          <div class="text-xs-center">
            <v-btn
              color="primary"
              @click="alert2 = !alert2"
              class="mt-3"
            >
              Toggle
            </v-btn>
          </div>
          <v-alert
            :value="alert2"
            type="info"
            transition="scale-transition"
            class="mb-3"
          >
            This is a info alert.
          </v-alert>
        </td>

        <td v-else-if="props.item.num == 4" colspan="2">
          <v-alert
            :value="true"
            color="warning"
            icon="warning"
            outline
            class="mt-3 mb-3"
          >
            This is an outline alert.
          </v-alert>
        </td>
        
      </tr>

    </template>
  </v-data-table>
</template>

<script>

  export default {
    data () {
      return {
        alert_list: [
          {
            value: false,
            name: '閉じるボタン付きアラート',
            text: "アラートに閉じるボタンをつける",
            url: "https://vuetifyjs.com/ja/components/alerts#example-closable",
            num: 1,
          },
          {
            value: false,
            name: 'アイコンの設定変更',
            text: "アラートのアイコンの変更や削除をする",
            url: "https://vuetifyjs.com/ja/components/alerts#example-icon",
            num: 2,
          },
          {
            value: false,
            name: 'トランジション設定',
            text: "アラート表示・非表示の際に、トランジションを設定する",
            url: "https://vuetifyjs.com/ja/components/alerts#example-transition",
            num: 3,
          },
          {
            value: false,
            name: 'アウトラインアラート',
            text: "現在適用されている色を境界線として表示したアラート",
            url: "https://vuetifyjs.com/ja/components/alerts#example-outline",
            num: 4,
          },
        ],
        alert: true,
        alert2: true,
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
  border-left:solid 1px #ddd;
  border-right:solid 1px #ddd;
}
</style>
