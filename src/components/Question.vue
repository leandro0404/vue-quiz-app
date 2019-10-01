<template>
    <div id="frame">
            
            <h2 class="pergunta" id="pergunta"> {{ anwswer.pergunta }}</h2>
            <p class="descricaoRespostaCorreta" id="descricaoRespostaCorreta">&nbsp;</p>
            <ul id="choice-block">   
                <li v-for="item in anwswer.respostas"  v-bind:key="item"  v-on:click="selected($event)"> {{ item }}</li>
            </ul>
            <div 
                class="choice-box" 
                id="submitbutton" 
            
                >OK</div>
            
    </div>
</template>

<script>
export default {
  name: 'Question',
  props: {
    anwswer : Object
  },
  methods:{
    selected (e) {
      debugger
      return null;
    }
  }

}
</script>
