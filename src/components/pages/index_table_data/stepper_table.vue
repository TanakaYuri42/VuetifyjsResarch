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
          <v-stepper v-model="e6" vertical>
            <v-stepper-step :complete="e6 > 1" step="1">
              Select an app
              <small>Summarize if needed</small>
            </v-stepper-step>

            <v-stepper-content step="1">
              <v-card color="grey lighten-1" class="mb-5" height="200px"></v-card>
              <v-btn color="primary" @click="e6 = 2">Continue</v-btn>
              <v-btn flat>Cancel</v-btn>
            </v-stepper-content>

            <v-stepper-step :complete="e6 > 2" step="2">Configure analytics for this app</v-stepper-step>

            <v-stepper-content step="2">
              <v-card color="grey lighten-1" class="mb-5" height="200px"></v-card>
              <v-btn color="primary" @click="e6 = 3">Continue</v-btn>
              <v-btn flat>Cancel</v-btn>
            </v-stepper-content>

            <v-stepper-step :complete="e6 > 3" step="3">Select an ad format and name ad unit</v-stepper-step>

            <v-stepper-content step="3">
              <v-card color="grey lighten-1" class="mb-5" height="200px"></v-card>
              <v-btn color="primary" @click="e6 = 4">Continue</v-btn>
              <v-btn flat>Cancel</v-btn>
            </v-stepper-content>

            <v-stepper-step step="4">View setup instructions</v-stepper-step>
            <v-stepper-content step="4">
              <v-card color="grey lighten-1" class="mb-5" height="200px"></v-card>
              <v-btn color="primary" @click="e6 = 1">Continue</v-btn>
              <v-btn flat>Cancel</v-btn>
            </v-stepper-content>
          </v-stepper>
        </td>


        <td v-else-if="props.item.num == 6" colspan="2" class="pt-2 pb-2">
          <div>
            <v-stepper>
              <v-stepper-header>
                <v-stepper-step step="1">Select campaign settings</v-stepper-step>

                <v-divider></v-divider>

                <v-stepper-step step="2">Create an ad group</v-stepper-step>

                <v-divider></v-divider>

                <v-stepper-step step="3">Create an ad</v-stepper-step>
              </v-stepper-header>
            </v-stepper>

            <v-stepper value="2" class="mt-2">
              <v-stepper-header>
                <v-stepper-step step="1" complete>Select campaign settings</v-stepper-step>

                <v-divider></v-divider>

                <v-stepper-step step="2">Create an ad group</v-stepper-step>

                <v-divider></v-divider>

                <v-stepper-step step="3">Create an ad</v-stepper-step>
              </v-stepper-header>
            </v-stepper>

            <v-stepper value="3" class="mt-2">
              <v-stepper-header>
                <v-stepper-step step="1" complete>Select campaign settings</v-stepper-step>

                <v-divider></v-divider>

                <v-stepper-step step="2" complete>Create an ad group</v-stepper-step>

                <v-divider></v-divider>

                <v-stepper-step step="3">Create an ad</v-stepper-step>
              </v-stepper-header>
            </v-stepper>
          </div>
        </td>


        <td v-else-if="props.item.num == 7" colspan="2" class="pt-2 pb-2">
          <div>
            <v-stepper non-linear>
              <v-stepper-header>
                <v-stepper-step
                  editable
                  step="1"
                >
                  Select campaign settings
                </v-stepper-step>

                <v-divider></v-divider>

                <v-stepper-step
                  editable
                  step="2"
                >
                  Create an ad group
                </v-stepper-step>

                <v-divider></v-divider>

                <v-stepper-step
                  step="3"
                  editable
                >
                  Create an ad
                </v-stepper-step>
              </v-stepper-header>
            </v-stepper>

            <v-stepper
              class="mt-2"
              non-linear
            >
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
                  editable
                  step="2"
                >
                  Create an ad group
                </v-stepper-step>

                <v-divider></v-divider>

                <v-stepper-step
                  complete
                  editable
                  step="3"
                >
                  Create an ad
                </v-stepper-step>
              </v-stepper-header>
            </v-stepper>

            <v-stepper
              class="mt-2"
              non-linear
              value="3"
            >
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
                  editable
                  step="2"
                >
                  Create an ad group
                </v-stepper-step>

                <v-divider></v-divider>

                <v-stepper-step
                  complete
                  editable
                  step="3"
                >
                  Create an ad
                </v-stepper-step>
              </v-stepper-header>
            </v-stepper>
          </div>
        </td>


        <td v-else-if="props.item.num == 8" colspan="2" class="pt-2 pb-2">
          <v-stepper>
            <v-stepper-header>
              <v-stepper-step step="1">Ad unit details</v-stepper-step>

              <v-divider></v-divider>

              <v-stepper-step :rules="[() => false]" step="2">
                Ad templates
                <small>Alert message</small>
              </v-stepper-step>

              <v-divider></v-divider>

              <v-stepper-step step="3">Ad sizes</v-stepper-step>
            </v-stepper-header>
          </v-stepper>
        </td>


        <td v-else-if="props.item.num == 9" colspan="2" class="pt-2 pb-2">
          <v-stepper alt-labels>
            <v-stepper-header>
              <v-stepper-step step="3" complete>Ad type</v-stepper-step>

              <v-divider></v-divider>

              <v-stepper-step step="4" complete>Ad style</v-stepper-step>

              <v-divider></v-divider>

              <v-stepper-step :rules="[() => false]" step="5">
                Custom channels
                <small>Alert message</small>
              </v-stepper-step>

              <v-divider></v-divider>

              <v-stepper-step step="6">Get code</v-stepper-step>
            </v-stepper-header>
          </v-stepper>
        </td>


        <td v-else-if="props.item.num == 10" colspan="2" class="pt-2 pb-2">
          <div>
            <v-card class="mb-3">
              <v-card-text>
                <div>{{ typeof steps }}</div>

                <v-text-field
                  :value="steps"
                  hint="This demo has a maximum of 6 steps"
                  label="# of steps"
                  max="6"
                  min="1"
                  persistent-hint
                  type="number"
                  @input="onInput"
                ></v-text-field>
              </v-card-text>
            </v-card>
            <v-stepper v-model="e1">
              <v-stepper-header>
                <template v-for="n in steps">
                  <v-stepper-step
                    :complete="e1 > n"
                    :key="`${n}-step`"
                    :step="n"
                    editable
                  >
                    Step {{ n }}
                  </v-stepper-step>

                  <v-divider
                    v-if="n !== steps"
                    :key="n"
                  ></v-divider>
                </template>
              </v-stepper-header>

              <v-stepper-items>
                <v-stepper-content
                  v-for="n in steps"
                  :key="`${n}-content`"
                  :step="n"
                >
                  <v-card
                    class="mb-5"
                    color="grey lighten-1"
                    height="200px"
                  ></v-card>

                  <v-btn
                    color="primary"
                    @click="nextStep(n)"
                  >
                    Continue
                  </v-btn>

                  <v-btn flat>Cancel</v-btn>
                </v-stepper-content>
              </v-stepper-items>
            </v-stepper>
          </div>
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
        e6: 1,
        e1: 1,
        steps: 2,
      }
    },
    watch: {
      steps (val) {
        if (this.e1 > val) {
          this.e1 = val
        }
      }
    },
    methods: {
      onInput (val) {
        this.steps = parseInt(val)
      },
      nextStep (n) {
        if (n === this.steps) {
          this.e1 = 1
        } else {
          this.e1 = n + 1
        }
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
