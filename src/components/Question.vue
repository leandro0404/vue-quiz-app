<template>
    <div id="frame">
            
            <h2 class="pergunta" id="pergunta"> {{ anwswer.pergunta }}</h2>
            <p class="descricaoRespostaCorreta" id="descricaoRespostaCorreta">&nbsp;</p>
            <ul id="choice-block">   
                <li  v-for="item in anwswer.respostas"  v-bind:key="item"  v-on:click="selected($event)"  class="choice choice-box"> {{ item }}</li>
            </ul>
            <div v-if="answered"
                class="choice-box" 
                id="submitbutton" 
             
                >OK</div>
            
    </div>
</template>

<script>
export default {
  name: 'Question',
  props: {
    anwswer : Object,
    answered : false
    
  },
  methods:{
    selected :function (e) {
     this.anwswer.respostaMarcada = e.target.innerText;
     this.answered = true;
    },
    confirm : function(){
      debugger
     
    }    
  }
}

</script>
