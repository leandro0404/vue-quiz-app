<template>
   <div id="frame">
            <p class="pager" id="pager">pergunta {{ questionsAnswered }} de  {{ questionsAnswered }} </p>
            <h2 class="pergunta" id="pergunta">Você acertou {{ score }} de {{ questionsAnswered }} Questões!</h2>
            <h2>{{ Math.round(score /questionsAnswered * 100) + '%'}} </h2><p class="descricaoRespostaCorreta" id="descricaoRespostaCorreta">
            </p><ul id="choice-block"></ul>
    </div>  
</template>

<script>
export default {
  name: 'Score',
  props: {
    score: Number,
    questionsAnswered: Number
  }
}
</script>