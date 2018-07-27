<template>
  <v-data-table
    :headers="headers"
    :items="stepper_list"
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
        <td v-if="props.item.num == 1" colspan="2" class="pt-2 pb-2">
          <v-stepper>
            <v-stepper-header>
              <v-stepper-step
                complete
                editable
                step="1"
              >
                Select campaign settings
              </v-stepper-step>

              <v-divider></v-divider>

              <v-stepper-step
                complete
                step="2"
              >Create an ad group</v-stepper-step>

              <v-divider></v-divider>

              <v-stepper-step
                step="3"
              >
                Create an ad
              </v-stepper-step>
            </v-stepper-header>
          </v-stepper>
        </td>


        <td v-else-if="props.item.num == 2" colspan="2" class="pt-2 pb-2">
          <v-stepper value="2">
            <v-stepper-header>
              <v-stepper-step step="1" complete>Select campaign settings</v-stepper-step>

              <v-divider></v-divider>

              <v-stepper-step step="2">Create an ad group</v-stepper-step>

              <v-divider></v-divider>

              <v-stepper-step step="3">Create an ad</v-stepper-step>
            </v-stepper-header>
          </v-stepper>
        </td>


        <td v-else-if="props.item.num == 3" colspan="2" class="pt-2 pb-2">
          <v-stepper value="2">
            <v-stepper-header>
              <v-stepper-step step="1" complete>Select campaign settings</v-stepper-step>

              <v-divider></v-divider>

              <v-stepper-step step="2">
                Create an ad group
                <small>Optional</small>
              </v-stepper-step>

              <v-divider></v-divider>

              <v-stepper-step step="3">Create an ad</v-stepper-step>
            </v-stepper-header>
          </v-stepper>
        </td>


        <td v-else-if="props.item.num == 4" colspan="2" class="pt-2 pb-2">
          <v-stepper value="1">
            <v-stepper-header>
              <v-stepper-step step="1">Select campaign settings</v-stepper-step>

              <v-divider></v-divider>

              <v-stepper-step step="2">Create an ad group</v-stepper-step>

              <v-divider></v-divider>

              <v-stepper-step step="3">Create an ad</v-stepper-step>
            </v-stepper-header>
          </v-stepper>
        </td>


        <td v-else-if="props.item.num == 5" colspan="2" class="pt-2 pb-2">
          
        </td>
        <td v-else-if="props.item.num == 6" colspan="2" class="pt-2 pb-2">
          
        </td>
        <td v-else-if="props.item.num == 7" colspan="2" class="pt-2 pb-2">

        </td>
        <td v-else-if="props.item.num == 8" colspan="2" class="pt-2 pb-2">
            
        </td>
        <td v-else-if="props.item.num == 9" colspan="2" class="pt-2 pb-2">
          
        </td>
        <td v-else-if="props.item.num == 10" colspan="2" class="pt-2 pb-2">
          
        </td>

      </tr>
    
    </template>
  </v-data-table>
</template>

<script>

  export default {
    data () {
      return {
        stepper_list: [
          {
            value: false,
            name: '編集可能なステップ',
            text: "編集可能なステップなら、ユーザーの選択で移動できる",
            url: "https://vuetifyjs.com/ja/components/steppers#example-editable",
            num: 1
          },  
          {
            value: false,
            name: '編集不可能なステップ',
            text: "ユーザーの選択で移動することはできず、ステップは直線的に進行する",
            url: "https://vuetifyjs.com/ja/components/steppers#example-non-editable",
            num: 2
          },  
          {
            value: false,
            name: 'オプションステップ',
            text: "サブテキストを読み込む",
            url: "https://vuetifyjs.com/ja/components/steppers#example-optional",
            num: 3
          },  
          {
            value: false,
            name: '水平ステップ',
            text: "定義されたステップを経て、x軸に沿って進行する",
            url: "https://vuetifyjs.com/ja/components/steppers#example-horizontal",
            num: 4,
          }, 
          {
            value: false,
            name: '垂直ステップ',
            text: "定義されたステップを経て、y軸に沿って進行する",
            url: "https://vuetifyjs.com/ja/components/steppers#example-vertical",
            num: 5
          },  
          {
            value: false,
            name: 'リニアステップ',
            text: "常に定義されたステップで進行する",
            url: "https://vuetifyjs.com/ja/components/steppers#example-linear",
            num: 6
          },  
          {
            value: false,
            name: '非リニアステップ',
            text: "ユーザーが選択した順番でステップが進行する",
            url: "https://vuetifyjs.com/ja/components/steppers#example-non-linear",
            num: 7
          },  
          {
            value: false,
            name: 'エラー表示',
            text: "エラーが起きた際に、それを表示する",
            url: "https://vuetifyjs.com/ja/components/steppers#example-error",
            num: 8
          },  
          {
            value: false,
            name: '代替ラベルによるエラー表示',
            text: "エラー状態を代替ラベルスタイルに適用する",
            url: "https://vuetifyjs.com/ja/components/steppers#example-alternate-error",
            num: 9
          },  
          {
            value: false,
            name: 'ダイナミックなステップ',
            text: "ユーザーの操作で、動的にステップを追加・削除する",
            url: "https://vuetifyjs.com/ja/components/steppers#example-dynamic",
            num: 10
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
