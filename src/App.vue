<template>
  <div id="app">
    <Login   v-model="email" v-if="email === null"/>
    <Question  v-if="email !== null"  :anwswer="anwswers[questionsAnswered]" />
  </div>
</template>

<script>
import Login from './components/Login.vue'
import Question from './components/Question.vue'
import data from './data/data.js'

export default {
  name: 'app',
  data () {
    return {
            score : 0,
            questionsAnswered :0,
            showConfirm : false,
            email : null,
            start :false,
            anwswers : data
    }
  },
  components: {
    Login,
    Question
  }
}
</script>
