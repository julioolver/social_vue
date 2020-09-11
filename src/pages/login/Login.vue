<template>

  <login-template>
    <span slot="menuesquerdo">
      <img src="https://cakeerp.com/wp-content/uploads/2019/10/capa-2-1080x675.png" class="responsive-img">
    </span>
    <span slot="principal">
     <h2>Login</h2>

      <input type="text" placeholder="E-mail" v-model="email">
      <input type="password" placeholder="Senha" v-model="password">
      <button class="btn" v-on:click="login()">Entrar</button>
      <router-link to="/cadastro"  class="btn orange">Cadastre-se</router-link>
    </span>

  </login-template>

</template>

<script>
import LoginTemplate from '@/templates/LoginTemplate'
import axios from 'axios';

export default {
  name: 'Login',
  data () {
    return {
      email: '',
      password: ''
    }
  },
  components: {
    LoginTemplate
  },
  methods: {
    login(){
      axios.post(`http://127.0.0.1:8000/api/usuario/login`, {
      email: this.email,
      password: this.password
    })
    .then(response => {
      console.log(response);
      if(response.data.token){
        // Login efetuado com sucesso
        console.log('Login efetuado com sucesso');
        sessionStorage.setItem('user', JSON.stringify(response.data));
        this.$router.push('/');
      } else if(response.data.status == false){
        //Login não existe
        alert('Login não existe');

      } else {
        alert('erros de validação');
        // erros de validação
        let erros = '';
        for(let erro of Object.values(response.data)){
          erros += erro + " ";
        }
        alert(erros);
      }
    })
    .catch(e => {
      //this.errors.push(e)
      alert('Erro! Tente novamente mais tarde!')
    })

    }
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
