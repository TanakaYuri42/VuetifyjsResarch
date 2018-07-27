<template>
  <v-data-table
    :headers="headers"
    :items="progresscircle_list"
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
        <v-progress-circular
          :value="100"
          color="red"
        ></v-progress-circular>
        &nbsp;&nbsp;&nbsp;
        <v-progress-circular
          :value="80"
          color="blue"
        ></v-progress-circular>
        &nbsp;&nbsp;&nbsp;
        <v-progress-circular
          :value="60"
          color="green"
        ></v-progress-circular>
      </td>

      <td v-else-if="props.item.num == 2" colspan="2">
        <v-progress-circular
          indeterminate
          color="yellow"
        ></v-progress-circular>
        &nbsp;&nbsp;&nbsp;
        <v-progress-circular
          indeterminate
          color="purple"
        ></v-progress-circular>
        &nbsp;&nbsp;&nbsp;
        <v-progress-circular
          indeterminate
        ></v-progress-circular>
      </td>

      <td v-else-if="props.item.num == 3" colspan="2">
        <v-progress-circular
          :value="25"
          :size="25"
          color="primary"
        ></v-progress-circular>
        &nbsp;&nbsp;&nbsp;
        <v-progress-circular
          :value="50"
          :size="40"
          color="primary"
        ></v-progress-circular>
        &nbsp;&nbsp;&nbsp;
        <v-progress-circular
          :value="75"
          :size="50"
          color="primary"
        ></v-progress-circular>
      </td>

      <td v-else-if="props.item.num == 4" colspan="2">
        <v-progress-circular
          :rotate="90"
          :size="40"
          :width="5"
          :value="value"
          color="red"
        >
          {{ value }}
        </v-progress-circular>
        &nbsp;&nbsp;&nbsp;
        <v-progress-circular
          :rotate="180"
          :size="50"
          :width="8"
          :value="value"
          color="pink"
        >
          {{ value }}
        </v-progress-circular>
      </td>

    
    </template>
  </v-data-table>
</template>

<script>

  export default {
    data () {
      return {
        progresscircle_list:[
          {
            value: false,
            name: '色の設定',
            text: "プログレスバーに色をつける",
            url: "https://vuetifyjs.com/ja/components/progress#example-circular-colored",
            num: 1,
          },  
          {
            value: false,
            name: '不確定',
            text: "進行の割合を不確定なプログレスバー。延々とアニメーションする",
            url: "https://vuetifyjs.com/ja/components/progress#example-circular-indeterminate",
            num: 2,
          }, 
          {
            value: false,
            name: 'サイズ変更',
            text: "プログレスバーのサイズを変更する",
            url: "https://vuetifyjs.com/ja/components/progress#example-circular-size-and-width",
            num: 3,
          },  
          {
            value: false,
            name: '回転',
            text: "プログレスバーを進行に合わせて回転させる",
            url: "https://vuetifyjs.com/ja/components/progress#example-circular-rotate",
            num: 4
          },  
        ],
        interval: {},
        value: 0,
      }
    },
    beforeDestroy () {
      clearInterval(this.interval)
    },
    mounted () {
      this.interval = setInterval(() => {
        if (this.value === 100) {
          return (this.value = 0)
        }
        this.value += 10
      }, 1000)
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
