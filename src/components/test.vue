<template>
  <v-content>
    <Comment/>
    <Button/>
    <h2>ステッパー | v-stepper</h2>
    <Stepper/>
    <Clock/>
    <Calender/>
    <Iterator/>
  </v-content>
</template>

<script>
import Button from './pages/button'
import Stepper from './pages/stepper'
import Clock from './pages/clock'
import Comment from './pages/comment'
import Calender from './pages/calender'
import Iterator from './pages/iterator'

export default {
  name: 'Test',
  components: {
    Button,
    Stepper,
    Clock,
    Comment,
    Calender,
    Iterator
  },
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h2 {
  text-align:center;
  margin-top:40px;
  background-color:#B2EBF2;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
