<template>
  <div id="app">
    <Login   
    v-model="email"
    v-if="email === null"/>
    <Question
     v-on:save="onSave"
     v-if="email !== null && !endGame"   
     :anwswer="anwswers[questionsAnswered]"  
     :questionsCount="questionsCount" 
     :questionsAnswered="questionsAnswered"/>
    <Score  
    :score='score' 
    :questionsAnswered="questionsAnswered"  
    v-if="endGame"/>
  </div>
</template>

<script>
import Login from './components/Login.vue'
import Question from './components/Question.vue'
import Score from './components/Score.vue'
import data from './data/data.vue'

export default {
  name: 'app',
  data () {
    return {
            score : 0,
            questionsAnswered :0,
            questionsCount : data.length,
            email : null,
            start :false,
            anwswers : data,
            endGame :false
    }
  },
    methods: {
    onSave: function () {
     this.questionsAnswered ++;
     this.onScore();
    },
    onScore :function(){
      let count = 0;
      this.anwswers.forEach(function(item,i){         
         if(item.respostaCorreta === item.respostaMarcada)
                       count++;  
      });
      this.score = count;
      if(this.questionsAnswered == this.anwswers.length)
      {
          this.endGame = true;
          setTimeout(() => {
            this.email = null;
             this.endGame =false;
          },3000);
      }
    }
  },
  components: {
    Login,
    Question,
    Score
  }
}
</script>