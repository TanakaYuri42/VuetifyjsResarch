<template>
  <v-card flat class="py-5">
    <v-card-text>
      <v-container fluid class="pa-0">
        <v-layout row wrap>
        <v-flex xs12 class="py-2">
            <h2>ボタン機能 | v-btn</h2>
            <v-divider></v-divider>
        </v-flex>
          <v-flex xs12 class="py-2">
            <v-btn color="success">Success</v-btn>
            <v-btn color="error">Error</v-btn>
            <v-btn color="warning">Warning</v-btn>
            <v-btn color="info">Info</v-btn>
          </v-flex>

          <v-flex xs12 class="py-2">
            <Dialog/>
          </v-flex>

          <v-flex xs12 class="py-2">
            <v-btn block color="secondary" dark>Block Button</v-btn>
          </v-flex>

          <v-flex xs12 class="py-2">
            <v-btn outline color="indigo">Outline Button</v-btn>
            <v-btn outline fab color="teal">
              <v-icon>list</v-icon>
            </v-btn>
            <v-btn outline large fab color="indigo">
              <v-icon>edit</v-icon>
            </v-btn>
            <v-btn round color="primary" dark>Rounded Button</v-btn>
          </v-flex>

          <v-flex xs12 sm6 class="py-2">
            <p>Exclusive</p>
            <v-btn-toggle v-model="toggle_exclusive">
              <v-btn flat>
                <v-icon>format_align_left</v-icon>
              </v-btn>
              <v-btn flat>
                <v-icon>format_align_center</v-icon>
              </v-btn>
              <v-btn flat>
                <v-icon>format_align_right</v-icon>
              </v-btn>
              <v-btn flat>
                <v-icon>format_align_justify</v-icon>
              </v-btn>
            </v-btn-toggle>
          </v-flex>

          <v-flex xs12 sm6 class="py-2">
            <p>Multiple</p>
            <v-btn-toggle v-model="toggle_multiple" multiple>
              <v-btn flat>
                <v-icon>format_bold</v-icon>
              </v-btn>
              <v-btn flat>
                <v-icon>format_italic</v-icon>
              </v-btn>
              <v-btn flat>
                <v-icon>format_underlined</v-icon>
              </v-btn>
              <v-btn flat>
                <v-icon>format_color_fill</v-icon>
              </v-btn>
            </v-btn-toggle>
          </v-flex>

          <v-flex xs12 sm6 class="py-2">
            <p>No Options Selected</p>
            <v-btn-toggle v-model="toggle_none">
              <v-btn flat>
                <v-icon>format_align_left</v-icon>
              </v-btn>
              <v-btn flat>
                <v-icon>format_align_center</v-icon>
              </v-btn>
              <v-btn flat>
                <v-icon>format_align_right</v-icon>
              </v-btn>
              <v-btn flat>
                <v-icon>format_align_justify</v-icon>
              </v-btn>
            </v-btn-toggle>
          </v-flex>

          <v-flex xs12 sm6 class="py-2">
            <p>Mandatory</p>
            <v-btn-toggle v-model="toggle_one" mandatory>
              <v-btn flat>
                <v-icon>format_align_left</v-icon>
              </v-btn>
              <v-btn flat>
                <v-icon>format_align_center</v-icon>
              </v-btn>
              <v-btn flat>
                <v-icon>format_align_right</v-icon>
              </v-btn>
              <v-btn flat>
                <v-icon>format_align_justify</v-icon>
              </v-btn>
            </v-btn-toggle>
          </v-flex>

          <v-flex xs12 sm6 class="py-2">
            <p>Text Options</p>
            <v-btn-toggle v-model="text">
              <v-btn flat value="left">
                Left
              </v-btn>
              <v-btn flat value="center">
                Center
              </v-btn>
              <v-btn flat value="right">
                Right
              </v-btn>
              <v-btn flat value="justify">
                Justify
              </v-btn>
            </v-btn-toggle>
          </v-flex>

          <v-flex xs12 sm6 class="py-2">
            <p>Text &amp; Icon Options</p>
            <v-btn-toggle v-model="icon">
              <v-btn flat value="left">
                <span>Left</span>
                <v-icon>format_align_left</v-icon>
              </v-btn>
              <v-btn flat value="center">
                <span>Center</span>
                <v-icon>format_align_center</v-icon>
              </v-btn>
              <v-btn flat value="right">
                <span>Right</span>
                <v-icon>format_align_right</v-icon>
              </v-btn>
              <v-btn flat value="justify">
                <span>Justify</span>
                <v-icon>format_align_justify</v-icon>
              </v-btn>
            </v-btn-toggle>
          </v-flex>
        </v-layout>
      </v-container>
    </v-card-text>
  </v-card>
</template>

<script>
  import Dialog from './dialog'
  export default {
    components: {
      Dialog
    },
    data () {
      return {
        text: 'center',
        icon: 'justify',
        toggle_none: null,
        toggle_one: 0,
        toggle_exclusive: 2,
        toggle_multiple: [0, 1, 2]
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