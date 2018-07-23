<template>
  <v-content>
    <Comment/>
    <Button/>
    <!-- <Icon/> -->
    <!-- <h2>ステッパー | v-stepper</h2>
    <Stepper/>
    <Clock/>
    <Calender/>
    <Iterator/> -->
    <h2>Component一覧表</h2>
    <Index/>
  </v-content>
</template>

<script>
import Button from './pages/button'
import Icon from './pages/icon'
import Stepper from './pages/stepper'
import Clock from './pages/clock'
import Comment from './pages/comment'
import Calender from './pages/calender'
import Iterator from './pages/iterator'
import Itiran from './pages/itiran'
import Index from './pages/index'

export default {
  name: 'Test',
  components: {
    Button,
    Icon,
    Stepper,
    Clock,
    Comment,
    Calender,
    Iterator,
    Itiran,
    Index
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
