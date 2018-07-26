<template>
  <v-content>
    <h2>Component一覧表</h2>
    <Index/>
    <Comment/>
    <Button/>
  </v-content>
</template>

<script>
import Button from './pages/button'
import Comment from './pages/comment'
import Index from './pages/index'

export default {
  name: 'Test',
  components: {
    Button,
    Comment,
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
