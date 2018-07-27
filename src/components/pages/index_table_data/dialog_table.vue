<template>
  <v-data-table
    :headers="headers"
    :items="dialog_list"
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
        <v-layout row justify-center>
          <v-dialog v-model="dialog1" persistent max-width="290">
            <v-btn slot="activator" color="primary" dark>Open Dialog</v-btn>
            <v-card>
              <v-card-title class="headline">Use Google's location service?</v-card-title>
              <v-card-text>Let Google help apps determine location. This means sending anonymous location data to Google, even when no apps are running.</v-card-text>
              <v-card-actions>
                <v-spacer></v-spacer>
                <v-btn color="green darken-1" flat @click.native="dialog1 = false">Disagree</v-btn>
                <v-btn color="green darken-1" flat @click.native="dialog1 = false">Agree</v-btn>
              </v-card-actions>
            </v-card>
          </v-dialog>
        </v-layout>
      </td>

      <td v-else-if="props.item.num == 2" colspan="2">          
        <v-layout row justify-center>
          <v-dialog v-model="dialog2" persistent max-width="500px">
            <v-btn slot="activator" color="primary" dark>Open Dialog</v-btn>
            <v-card>
              <v-card-title>
                <span class="headline">User Profile</span>
              </v-card-title>
              <v-card-text>
                <v-container grid-list-md>
                  <v-layout wrap>
                    <v-flex xs12 sm6 md4>
                      <v-text-field label="Legal first name" required></v-text-field>
                    </v-flex>
                    <v-flex xs12 sm6 md4>
                      <v-text-field label="Legal middle name" hint="example of helper text only on focus"></v-text-field>
                    </v-flex>
                    <v-flex xs12 sm6 md4>
                      <v-text-field
                        label="Legal last name"
                        hint="example of persistent helper text"
                        persistent-hint
                        required
                      ></v-text-field>
                    </v-flex>
                    <v-flex xs12>
                      <v-text-field label="Email" required></v-text-field>
                    </v-flex>
                    <v-flex xs12>
                      <v-text-field label="Password" type="password" required></v-text-field>
                    </v-flex>
                    <v-flex xs12 sm6>
                      <v-select
                        :items="['0-17', '18-29', '30-54', '54+']"
                        label="Age"
                        required
                      ></v-select>
                    </v-flex>
                    <v-flex xs12 sm6>
                      <v-autocomplete
                        :items="['Skiing', 'Ice hockey', 'Soccer', 'Basketball', 'Hockey', 'Reading', 'Writing', 'Coding', 'Basejump']"
                        label="Interests"
                        multiple
                        chips
                      ></v-autocomplete>
                    </v-flex>
                  </v-layout>
                </v-container>
                <small>*indicates required field</small>
              </v-card-text>
              <v-card-actions>
                <v-spacer></v-spacer>
                <v-btn color="blue darken-1" flat @click.native="dialog2 = false">Close</v-btn>
                <v-btn color="blue darken-1" flat @click.native="dialog2 = false">Save</v-btn>
              </v-card-actions>
            </v-card>
          </v-dialog>
        </v-layout>
      </td>


      <td v-else-if="props.item.num == 3" colspan="2">
        <v-layout row justify-center>
          <v-dialog v-model="dialog3" scrollable max-width="300px">
            <v-btn slot="activator" color="primary" dark>Open Dialog</v-btn>
            <v-card>
              <v-card-title>Select Country</v-card-title>
              <v-divider></v-divider>
              <v-card-text style="height: 300px;">
                <v-radio-group v-model="dialogm1" column>
                  <v-radio label="Bahamas, The" value="bahamas"></v-radio>
                  <v-radio label="Bahrain" value="bahrain"></v-radio>
                  <v-radio label="Bangladesh" value="bangladesh"></v-radio>
                  <v-radio label="Barbados" value="barbados"></v-radio>
                  <v-radio label="Belarus" value="belarus"></v-radio>
                  <v-radio label="Belgium" value="belgium"></v-radio>
                  <v-radio label="Belize" value="belize"></v-radio>
                  <v-radio label="Benin" value="benin"></v-radio>
                  <v-radio label="Bhutan" value="bhutan"></v-radio>
                  <v-radio label="Bolivia" value="bolivia"></v-radio>
                  <v-radio label="Bosnia and Herzegovina" value="bosnia"></v-radio>
                  <v-radio label="Botswana" value="botswana"></v-radio>
                  <v-radio label="Brazil" value="brazil"></v-radio>
                  <v-radio label="Brunei" value="brunei"></v-radio>
                  <v-radio label="Bulgaria" value="bulgaria"></v-radio>
                  <v-radio label="Burkina Faso" value="burkina"></v-radio>
                  <v-radio label="Burma" value="burma"></v-radio>
                  <v-radio label="Burundi" value="burundi"></v-radio>
                </v-radio-group>
              </v-card-text>
              <v-divider></v-divider>
              <v-card-actions>
                <v-btn color="blue darken-1" flat @click.native="dialog3 = false">Close</v-btn>
                <v-btn color="blue darken-1" flat @click.native="dialog3 = false">Save</v-btn>
              </v-card-actions>
            </v-card>
          </v-dialog>
        </v-layout>  
      </td>


      <td v-else-if="props.item.num == 4" colspan="2">
        <v-layout row justify-center>
          <v-dialog v-model="dialog4" width="600px">
            <v-btn slot="activator" color="primary" dark>Open Dialog</v-btn>
            <v-card>
              <v-card-title>
                <span class="headline">Use Google's location service?</span>
              </v-card-title>
              <v-card-text>Lorem ipsum dolor sit amet, semper quis, sapien id natoque elit. Nostra urna at, magna at neque sed sed ante imperdiet, dolor mauris cursus velit, velit non, sem nec. Volutpat sem ridiculus placerat leo, augue in, duis erat proin condimentum in a eget, sed fermentum sed vestibulum varius ac, vestibulum volutpat orci ut elit eget tortor. Ultrices nascetur nulla gravida ante arcu. Pharetra rhoncus morbi ipsum, nunc tempor debitis, ipsum pellentesque, vitae id quam ut mauris dui tempor, aptent non. Quisque turpis. Phasellus quis lectus luctus orci eget rhoncus. Amet donec vestibulum mattis commodo, nulla aliquet, nibh praesent, elementum nulla. Sit lacus pharetra tempus magna neque pellentesque, nulla vel erat.
              Justo ex quisque nulla accusamus venenatis, sed quis. Nibh phasellus gravida metus in, fusce aenean ut erat commodo eros. Ut turpis, dui integer, nonummy pede placeat nec in sit leo. Faucibus porttitor illo taciti odio, amet viverra scelerisque quis quis et tortor, curabitur morbi a. Enim tempor at, rutrum elit condimentum, amet rutrum vitae tempor torquent nunc. Praesent vestibulum integer maxime felis. Neque aenean quia vitae nostra, tempus elit enim id dui, at egestas pulvinar. Integer libero vestibulum, quis blandit scelerisque mattis fermentum nulla, tortor donec vestibulum dolor amet eget, elit nullam. Aliquam leo phasellus aliquam curabitur metus a, nulla justo mattis duis interdum vel, mollis vitae et id, vestibulum erat ridiculus sit pulvinar justo sed. Vehicula convallis, et nulla wisi, amet vestibulum risus, quam ac egestas.
              Et vitae, nulla gravida erat scelerisque nullam nunc pellentesque, a dictumst cras augue, purus imperdiet non. Varius montes cursus varius vel tortor, nec leo a qui, magni cras, velit vel consectetuer lobortis vel. Nibh erat et wisi felis leo porttitor, sapien nibh sapien pede mi, sed eget porttitor, repellendus arcu ac quis. Luctus vulputate aut est sem magna, placerat accumsan nunc vestibulum ipsum ac auctor, maecenas lorem in ut nec mauris tortor, doloribus varius sem tortor vestibulum mollis, eleifend tortor felis tempus lacus eu eu. Eleifend vel eu, nullam maecenas mauris nec nunc euismod, tortor porta ridiculus potenti, massa tristique nam magna, et wisi placerat et erat ante. Eget pede erat in facilisis, fermentum venenatis sodales. Ac tortor sociis et non animi tristique, rhoncus malesuada, ut arcu volutpat scelerisque sollicitudin, elit curabitur dui pede purus dolor, integer aenean risus taciti nulla eleifend accumsan. At pulvinar diam parturient, interdum mi velit aliquet et a. Arcu at ac placerat eget justo semper, purus sociis curabitur mi ipsum consequat ut, mollis vestibulum, est ante ornare lacus sem. Neque magna mauris, commodo quisque, praesent semper suscipit lobortis nam. Justo malesuada cursus ac nunc litora nunc. Tellus ac, in lobortis nunc, montes lectus purus fermentum.
              Ac sit wisi. Sodales aliquam, sed vestibulum nullam arcu sit risus arcu, id luctus vitae lorem nibh, integer nec nullam class cursus mi, purus arcu lectus. Vel ante suscipit volutpat potenti mattis sed, wisi eu placerat aliquam erat, lectus morbi lobortis at assumenda. Consequat neque purus ipsum voluptas odio, netus vestibulum ut nec, suspendisse pellentesque nec enim in. Wisi dictum sed semper a, ipsum erat tellus habitasse est, erat sem ornare, vitae quisque ultricies. Dui sed blandit. Tempor et faucibus justo sed luctus, nec vitae vitae. Nunc nibh pede, ipsum vestibulum aenean leo ante ultricies, nam cras quis sed penatibus amet. In mauris a. Integer metus mauris tortor, et rutrum vestibulum ultricies, ut phasellus in ullamcorper ut mollit, eu justo. Cursus pretium venenatis.
              Cras pellentesque vel sodales accumsan aenean. Feugiat metus sit nec in aliquet amet, porttitor pretium vulputate massa. Consequat ipsum luctus quisque adipiscing libero. Wisi sollicitudin. Eget vitae ac lobortis, lorem natoque vestibulum et, aliquet faucibus at morbi nibh, vel condimentum. Massa unde orci sed id sed, odio donec congue nec praesent amet. Hymenaeos velit lacus, quis vivamus libero tempus duis, eu nisi eu, ipsum at accumsan pede justo morbi donec, massa et libero sit risus neque tortor. Ut sed sed etiam hendrerit dapibus, quis metus suspendisse nibh.
              Fringilla tempor felis augue magna. Cum arcu a, id vitae. Pellentesque pharetra in cras sociis adipiscing est. Nibh nec mattis at maecenas, nisl orci aliquam nulla justo egestas venenatis, elementum duis vel porta eros, massa vitae, eligendi imperdiet amet. Nec neque luctus suscipit, justo sem praesent, ut nisl quisque, volutpat torquent wisi tellus aliquam reprehenderit, curabitur cras at quis massa porttitor mauris. Eros sed ultrices. Amet dignissim justo urna feugiat mauris litora, etiam accumsan, lobortis a orci suspendisse. Semper ac mauris, varius bibendum pretium, orci urna nunc ullamcorper auctor, saepe sem integer quam, at feugiat egestas duis. Urna ligula ante. Leo elementum nonummy. Sagittis mauris est in ipsum, nulla amet non justo, proin id potenti platea posuere sit ut, nunc sit erat bibendum. Nibh id auctor, ab nulla vivamus ultrices, posuere morbi nunc tellus gravida vivamus.
              Mauris nec, facilisi quam fermentum, ut mauris integer, orci tellus tempus diam ut in pellentesque. Wisi faucibus tempor et odio leo diam, eleifend quis integer curabitur sit scelerisque ac, mauris consequat luctus quam penatibus fringilla dis, vitae lacus in, est eu ac tempus. Consectetuer amet ipsum amet dui, sed blandit id sed. Tellus integer, dignissim id pede sodales quis, felis dolorem id mauris orci, orci tempus ut. Nullam hymenaeos. Curabitur in a, tortor ut praesent placerat tincidunt interdum, ac dignissim metus nonummy hendrerit wisi, etiam ut.
              Semper praesent integer fusce, tortor suspendisse, augue ligula orci ante asperiores ullamcorper. In sit per mi sed sed, mi vestibulum mus nam, morbi mauris neque vitae aliquam proin senectus. Ac amet arcu mollis ante congue elementum, inceptos eget optio quam pellentesque quis lobortis, sollicitudin sed vestibulum sollicitudin, lectus parturient nullam, leo orci ligula ultrices. At tincidunt enim, suspendisse est sit sem ac. Amet tellus molestie est purus magna augue, non etiam et in wisi id. Non commodo, metus lorem facilisi lobortis ac velit, montes neque sed risus consectetuer fringilla dolor. Quam justo et integer aliquam, cursus nulla enim orci, nam cursus adipiscing, integer torquent non, fringilla per maecenas. Libero ipsum sed tellus purus et. Duis molestie placerat erat donec ut. Dolor enim erat massa faucibus ultrices in, ante ultricies orci lacus, libero consectetuer mauris magna feugiat neque dapibus, donec pretium et. Aptent dui, aliquam et et amet nostra ligula.
              Augue curabitur duis dui volutpat, tempus sed ut pede donec. Interdum luctus, lectus nulla aenean elit, id sit magna, vulputate ultrices pellentesque vel id fermentum morbi. Tortor et. Adipiscing augue lorem cum non lacus, rutrum sodales laoreet duis tortor, modi placerat facilisis et malesuada eros ipsum, vehicula tempus. Ac vivamus amet non aliquam venenatis lectus, sociosqu adipiscing consequat nec arcu odio. Blandit orci nec nec, posuere in pretium, enim ut, consectetuer nullam urna, risus vel. Nullam odio vehicula massa sed, etiam sociis mauris, lacus ullamcorper, libero imperdiet non sodales placerat justo vehicula. Nec morbi imperdiet. Fermentum sem libero iaculis bibendum et eros, eget maecenas non nunc, ad pellentesque. Ut nec diam elementum interdum. Elementum vitae tellus lacus vitae, ipsum phasellus, corporis vehicula in ac sed massa vivamus, rutrum elit, ultricies metus volutpat.
              Semper wisi et, sollicitudin nunc vestibulum, cursus accumsan nunc pede tempus mi ipsum, ligula sed. Non condimentum ac dolor sit. Mollis eu aliquam, vel mattis mollis massa ut dolor ante, tempus lacinia arcu. Urna vestibulum lorem, nulla fermentum, iaculis ut congue ac vivamus. Nam libero orci, pulvinar nulla, enim pellentesque consectetuer leo, feugiat rhoncus rhoncus vel. Magna sociosqu donec, dictum cursus ullamcorper viverra. Ultricies quis orci lorem, suspendisse ut vestibulum integer, purus sed lorem pulvinar habitasse turpis.
              +</v-card-text>
              <v-card-actions>
                <v-spacer></v-spacer>
                <v-btn color="green darken-1" flat="flat" @click="dialog4 = false">Disagree</v-btn>
                <v-btn color="green darken-1" flat="flat" @click="dialog4 = false">Agree</v-btn>
              </v-card-actions>
            </v-card>
          </v-dialog>
        </v-layout>
      </td>


      <td v-else-if="props.item.num == 5" colspan="2">
        <div class="text-xs-center">
          <v-btn
            :disabled="dialog5"
            :loading="dialog5"
            class="white--text"
            color="primary"
            @click.stop="dialog5 = true"
          >
            Open Dialog
          </v-btn>
          <v-dialog
            v-model="dialog5"
            hide-overlay
            persistent
            width="300"
          >
            <v-card
              color="primary"
              dark
            >
              <v-card-text>
                Please stand by
                <v-progress-linear
                  indeterminate
                  color="white"
                  class="mb-0"
                ></v-progress-linear>
              </v-card-text>
            </v-card>
          </v-dialog>
        </div>
      </td>
 
    
    </template>
  </v-data-table>
</template>

<script>

  export default {
    data () {
      return {
        dialog_list: [
          {
            value: false,
            name: 'モーダル',
            text: "ダイアログ画面外をクリックしても、閉じないようにする",
            url: "https://vuetifyjs.com/ja/components/dialogs#example-modal",
            num: 1,
          }, 
          {
            value: false,
            name: 'フォーム',
            text: "ダイアログ画面にフォーム（form）を取り入れる",
            url: "https://vuetifyjs.com/ja/components/dialogs#example-form",
            num: 2,
          },  
          {
            value: false,
            name: 'スクロール',
            text: "ダイアログ画面内でスクロールできるようにする",
            url: "https://vuetifyjs.com/ja/components/dialogs#example-scrollable",
            num: 3,
          }, 
          {
            value: false,
            name: 'オーバーフロー',
            text: "ウィンドウ画面に収まらないダイアログ画面はスクロールする",
            url: "https://vuetifyjs.com/ja/components/dialogs#example-overflowed",
            num: 4,
          }, 
          {
            value: false,
            name: 'ローディング',
            text: "処理中であることをダイアログで表示する",
            url: "https://vuetifyjs.com/ja/components/dialogs#example-loader",
            num: 5,
          },  
        ],
        dialog1: false,
        dialog2: false,
        dialogm1: '',
        dialog3: false,
        dialog4: false,
        dialog5: false
      }
    },
    watch: {
      dialog5 (val) {
        if (!val) return

        setTimeout(() => (this.dialog5 = false), 4000)
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
