<template>
   <div id="frame">
            <p class="pager" id="pager">pergunta {{ questionsAnswered }} de  {{ anwswers }} </p>
            <h2 class="pergunta" id="pergunta">Você acertou {{ score }} de {{ anwswers }} Questões!</h2>
            <h2>{{ Math.round(score /anwswers * 100) + '%'}} </h2><p class="descricaoRespostaCorreta" id="descricaoRespostaCorreta">
            </p><ul id="choice-block"></ul>
    </div>  
</template>

<script>
export default {

}
</script>