<template>
    <div id="frame">   
      <p class="pager" id="pager">pergunta {{ (questionsAnswered)+1 }} de  {{ questionsCount }} </p>         
        <h2 class="pergunta" id="pergunta"> {{ anwswer.pergunta }}</h2>
        <p class="descricaoRespostaCorreta" id="descricaoRespostaCorreta">&nbsp;</p>
        <ul id="choice-block">   
            <li  v-for="item in anwswer.respostas"  v-bind:key="item"  @click="selected($event)"  class="choice choice-box"> {{ item }}</li>
        </ul>
        <div v-if="showConfirm"
            class="choice-box" 
            id="submitbutton" 
              @click="$emit('save')" 
            >OK</div>            
    </div>
</template>

<script>
export default {
  name: 'Question',
  data(){
     return {
       showConfirm : false
     }
  },
  props: {
    anwswer : Object,
    questionsAnswered : Number,
    questionsCount : Number
    
  },
  methods:{
    selected :function (e) {
     this.anwswer.respostaMarcada = e.target.innerText;
     this.showConfirm = true;
    }
  }
}

</script>
