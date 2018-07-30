<template>
  <v-data-table
    :headers="headers"
    :items="card_list"
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
          <v-layout>
            <v-flex xs12 sm6 offset-sm3>
              <v-card style="border:solid 2px #ddd">
                <v-card-media
                  class="white--text"
                  height="200px"
                  src="https://cdn.vuetifyjs.com/images/cards/docks.jpg"
                >
                  <v-container fill-height fluid>
                    <v-layout fill-height>
                      <v-flex xs12 align-end flexbox>
                        <span class="headline">Top 10 Australian beaches</span>
                      </v-flex>
                    </v-layout>
                  </v-container>
                </v-card-media>
                <v-card-title>
                  <div>
                    <span class="grey--text">Number 10</span><br>
                    <span>Whitehaven Beach</span><br>
                    <span>Whitsunday Island, Whitsunday Islands</span>
                  </div>
                </v-card-title>
                <v-card-actions>
                  <v-btn flat color="orange">Share</v-btn>
                  <v-btn flat color="orange">Explore</v-btn>
                </v-card-actions>
              </v-card>
            </v-flex>
          </v-layout>
        </td>


        <td v-else-if="props.item.num == 2" colspan="2" class="pt-2 pb-2">
          <div
            id="e3"
            style="max-width: 400px; margin: auto;"
            class="grey lighten-3"
          >
            <v-toolbar
              color="pink"
              dark
            >
              <v-toolbar-side-icon></v-toolbar-side-icon>
              <v-toolbar-title>My Music</v-toolbar-title>
              <v-spacer></v-spacer>
              <v-btn icon>
                <v-icon>search</v-icon>
              </v-btn>
            </v-toolbar>

            <v-card style="border:solid 2px #ddd">
              <v-container
                fluid
                grid-list-lg
              >
                <v-layout row wrap>
                  <v-flex xs12>
                    <v-card color="blue-grey darken-2" class="white--text">
                      <v-card-title primary-title>
                        <div class="headline">Unlimited music now</div>
                        <div>Listen to your favorite artists and albums whenever and wherever, online and offline.</div>
                      </v-card-title>
                      <v-card-actions>
                        <v-btn flat dark>Listen now</v-btn>
                      </v-card-actions>
                    </v-card>
                  </v-flex>

                  <v-flex xs12>
                    <v-card color="cyan darken-2" class="white--text">
                      <v-layout>
                        <v-flex xs5>
                          <v-card-media
                            src="https://cdn.vuetifyjs.com/images/cards/foster.jpg"
                            height="125px"
                            contain
                          ></v-card-media>
                        </v-flex>
                        <v-flex xs7>
                          <v-card-title primary-title>
                            <div>
                              <div class="headline">Supermodel</div>
                              <div>Foster the People</div>
                              <div>(2014)</div>
                            </div>
                          </v-card-title>
                        </v-flex>
                      </v-layout>
                      <v-divider light></v-divider>
                      <v-card-actions class="pa-3">
                        Rate this album
                        <v-spacer></v-spacer>
                        <v-icon>star_border</v-icon>
                        <v-icon>star_border</v-icon>
                        <v-icon>star_border</v-icon>
                        <v-icon>star_border</v-icon>
                        <v-icon>star_border</v-icon>
                      </v-card-actions>
                    </v-card>
                  </v-flex>

                  <v-flex xs12>
                    <v-card color="purple" class="white--text">
                      <v-layout row>
                        <v-flex xs7>
                          <v-card-title primary-title>
                            <div>
                              <div class="headline">Halycon Days</div>
                              <div>Ellie Goulding</div>
                              <div>(2013)</div>
                            </div>
                          </v-card-title>
                        </v-flex>
                        <v-flex xs5>
                          <v-card-media
                            src="https://cdn.vuetifyjs.com/images/cards/halcyon.png"
                            height="125px"
                            contain
                          ></v-card-media>
                        </v-flex>
                      </v-layout>
                      <v-divider light></v-divider>
                      <v-card-actions class="pa-3">
                        Rate this album
                        <v-spacer></v-spacer>
                        <v-icon>star_border</v-icon>
                        <v-icon>star_border</v-icon>
                        <v-icon>star_border</v-icon>
                        <v-icon>star_border</v-icon>
                        <v-icon>star_border</v-icon>
                      </v-card-actions>
                    </v-card>
                  </v-flex>
                </v-layout>
              </v-container>
            </v-card>
          </div>
        </td>


        <td v-else-if="props.item.num == 3" colspan="2" class="pt-2 pb-2">
          <v-layout column style="width:100%;margin: auto;">
            <v-flex xs12 sm6 offset-sm3>
              <v-toolbar color="indigo" dark>
                <v-toolbar-side-icon></v-toolbar-side-icon>
                <v-toolbar-title>Discover</v-toolbar-title>
                <v-spacer></v-spacer>
                <v-btn icon>
                  <v-icon>search</v-icon>
                </v-btn>
              </v-toolbar>

              <v-card style="border:solid 2px #ddd">
                <v-container
                  fluid
                  grid-list-md
                >
                  <v-layout row wrap>
                    <v-flex
                      v-for="card in cards"
                      v-bind="{ [`xs${card.flex}`]: true }"
                      :key="card.title"
                    >
                      <v-card>
                        <v-card-media
                          :src="card.src"
                          height="200px"
                        >
                          <v-container
                            fill-height
                            fluid
                            pa-2
                          >
                            <v-layout fill-height>
                              <v-flex xs12 align-end flexbox>
                                <span class="headline white--text" v-text="card.title"></span>
                              </v-flex>
                            </v-layout>
                          </v-container>
                        </v-card-media>

                        <v-card-actions>
                          <v-spacer></v-spacer>
                          <v-btn icon>
                            <v-icon>favorite</v-icon>
                          </v-btn>
                          <v-btn icon>
                            <v-icon>bookmark</v-icon>
                          </v-btn>
                          <v-btn icon>
                            <v-icon>share</v-icon>
                          </v-btn>
                        </v-card-actions>
                      </v-card>
                    </v-flex>
                  </v-layout>
                </v-container>
              </v-card>
            </v-flex>
          </v-layout>
        </td>


        <td v-else-if="props.item.num == 4" colspan="2" class="pt-2 pb-2">
          <v-layout row>
            <v-flex xs12 sm6 offset-sm3>
              <v-card style="border:solid 2px #ddd">
                <v-card-media
                  src="https://cdn.vuetifyjs.com/images/cards/sunshine.jpg"
                  height="200px"
                >
                </v-card-media>

                <v-card-title primary-title>
                  <div>
                    <div class="headline">Top western road trips</div>
                    <span class="grey--text">1,000 miles of wonder</span>
                  </div>
                </v-card-title>

                <v-card-actions>
                  <v-btn flat>Share</v-btn>
                  <v-btn flat color="purple">Explore</v-btn>
                  <v-spacer></v-spacer>
                  <v-btn icon @click="show = !show">
                    <v-icon>{{ show ? 'keyboard_arrow_down' : 'keyboard_arrow_up' }}</v-icon>
                  </v-btn>
                </v-card-actions>

                <v-slide-y-transition>
                  <v-card-text v-show="show">
                    I'm a thing. But, like most politicians, he promised more than he could deliver. You won't have time for sleeping, soldier, not with all the bed making you'll be doing. Then we'll go with that data file! Hey, you add a one and two zeros to that or we walk! You're going to do his laundry? I've got to find a way to escape.
                  </v-card-text>
                </v-slide-y-transition>
              </v-card>
            </v-flex>
          </v-layout>
        </td>


      </tr>
    
    </template>
  </v-data-table>
</template>

<script>

  export default {
    data () {
      return {
        card_list: [
          {
            value: false,
            name: 'テキスト付きメディア',
            text: "画像上などの、背景にテキストを表示する",
            url: "https://vuetifyjs.com/ja/components/cards#example-media-with-text",
            num: 1,
          },  
          {
            value: false,
            name: '水平型カード',
            text: "水平型にカスタマイズされたカード",
            url: "https://vuetifyjs.com/ja/components/cards#example-horizontal",
            num: 2,
          },  
          {
            value: false,
            name: 'グリッドリスト',
            text: "グリッドを使って、カードのレイアウトを整える",
            url: "https://vuetifyjs.com/ja/components/cards#example-grids",
            num: 3,
          },  
          {
            value: false,
            name: '開閉可能なテキストの追加',
            text: "選択するまで閉じられた状態の補助的なテキストを追加する",
            url: "https://vuetifyjs.com/ja/components/cards#example-custom-actions",
            num: 4
          },  
        ], 
        cards: [
          { title: 'Pre-fab homes', src: 'https://cdn.vuetifyjs.com/images/cards/house.jpg', flex: 12 },
          { title: 'Favorite road trips', src: 'https://cdn.vuetifyjs.com/images/cards/road.jpg', flex: 6 },
          { title: 'Best airlines', src: 'https://cdn.vuetifyjs.com/images/cards/plane.jpg', flex: 6 }
        ]   
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
