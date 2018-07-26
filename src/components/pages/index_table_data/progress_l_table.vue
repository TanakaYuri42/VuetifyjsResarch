<template>
  <v-data-table
    :headers="headers"
    :items="progressliner_list"
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
          <v-progress-linear value="30"></v-progress-linear>
          <v-progress-linear value="50"></v-progress-linear>
          <v-progress-linear value="80"></v-progress-linear>
        </td>

        <td v-else-if="props.item.num == 2" colspan="2">
          <v-progress-linear :indeterminate="true"></v-progress-linear>
        </td>

        <td v-else-if="props.item.num == 3" colspan="2">
          <v-progress-linear
            v-model="buffer"
            :buffer-value="bufferValue"
            buffer
          ></v-progress-linear>
        </td>

        <td v-else-if="props.item.num == 4" colspan="2">
          <v-progress-linear
            color="green"
            height="5"
            value="25"
          ></v-progress-linear>
          <v-progress-linear
            color="yellow"
            height="10"
            value="50"
          ></v-progress-linear>
          <v-progress-linear
            color="red"
            height="25"
            value="75"
          ></v-progress-linear>
        </td>

        <td v-else-if="props.item.num == 5" colspan="2">
          <v-progress-linear
            background-color="pink lighten-3"
            color="pink lighten-1"
            value="15"
          ></v-progress-linear>
          <v-progress-linear
            background-color="blue-grey"
            color="lime"
            value="30"
          ></v-progress-linear>
          <v-progress-linear
            background-color="success"
            color="error"
            value="45"
          ></v-progress-linear>
        </td>

      </tr>
    
    </template>
  </v-data-table>
</template>

<script>

  export default {
    data () {
      return {
        progressliner_list: [
          {
            value: false,
            name: '確定',
            text: "進行の割合が確定しているプログレスバー",
            url: "https://vuetifyjs.com/ja/components/progress#example-linear-determinate",
            num: 1,
          },  
          {
            value: false,
            name: '不確定',
            text: "進行の割合が不確定なプログレスバー。延々とアニメーションする",
            url: "https://vuetifyjs.com/ja/components/progress#example-linear-indeterminate",
            num: 2,
          },  
          {
            value: false,
            name: 'バッファ',
            text: "バッファを取り入れる",
            url: "https://vuetifyjs.com/ja/components/progress#example-linear-buffer",
            num: 3,
          },
          {
            value: false,
            name: '高さ・色の設定',
            text: "プログレスバーの高さや色を設定する",
            url: "https://vuetifyjs.com/ja/components/progress#example-linear-custom-height-and-contextual-colors",
            num: 4
          },  
          {
            value: false,
            name: '進行バーの色・背景色の設定',
            text: "プログレスバーの進行中のバーの色と背景色を設定する",
            url: "https://vuetifyjs.com/ja/components/progress#example-linear-custom-colors",
            num: 5
          },  
        ],
        value: 0,
        buffer: 10,
        bufferValue: 20,
        interval: 0,
      }
    },
    mounted () {
      this.startBuffer()
    },

    beforeDestroy () {
      clearInterval(this.interval)
    },

    methods: {
      startBuffer () {
        this.interval = setInterval(() => {
          this.buffer += Math.random() * (15 - 5) + 5
          this.bufferValue += Math.random() * (15 - 5) + 5
        }, 2000)
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
