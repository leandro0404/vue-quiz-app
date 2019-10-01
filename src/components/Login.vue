<template>
        <div id="frame">
             <img  class="login-logo" alt="Vue logo" src="../assets/logo.png">
            <h3 class="login-title">Este desafio consiste em responder um Quiz técnico sobre o tema desta oficina. Entre com seu email para iniciar o desafio.</h3>
                <form id="form-login" class="form-inline">
                <input  id="email" type="text" v-bind:value="email"  placeholder="Digite seu e-mail" class="form-control"/>
                <button type="button" id="start" name="start" class="btn btn-primary" @click="updateValue" >Iniciar</button>
                </form>
        </div>          
</template>

<script>

  function isEmail(email){
      
      var regex = /^([a-zA-Z0-9_.+-])+\@(([a-zA-Z0-9-])+\.)+([a-zA-Z0-9]{2,4})+$/;
      return regex.test(email);

    }

export default {
  name: 'Login',
  props: {
    email: String
  },
   methods: {
    updateValue: function () {
    
     if(isEmail(document.getElementById("email").value))
      this.$emit('input', document.getElementById("email").value);
    },
   
  }
}
</script>