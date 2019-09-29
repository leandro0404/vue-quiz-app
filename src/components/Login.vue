<template>
        <div id="frame">
             <img alt="Vue logo" src="../assets/logo.png">
            <h3 className="login-title">Este desafio consiste em responder um Quiz técnico sobre o tema desta oficina. Entre com seu email para iniciar o desafio.</h3>
                <form id="form-login" className="form-inline">
                <input type="text" id="email" name="email" placeholder="Digite seu e-mail" className="form-control"/>
                <button type="button" id="start" name="start" className="btn btn-primary" onClick={this.isEmailClick.bind(this)} >Iniciar</button>
                </form>
        </div>  
</template>

<script>
export default {
  name: 'Login',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
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
