<template>
  <login-template>
    <span slot="menuesquerdo">
      <img
        src="https://cakeerp.com/wp-content/uploads/2019/10/capa-2-1080x675.png"
        class="responsive-img"
      />
    </span>
    <span slot="principal">
      <h2>Cadastro</h2>
      <input type="text" placeholder="Nome" v-model="user.name" />
      <input type="text" placeholder="E-mail" v-model="user.email" />
      <input type="password" placeholder="Senha" v-model="user.password" />
      <input type="password" placeholder="Confirme sua Senha" v-model="user.password_confirmation " />
      <button class="btn" v-on:click="cadastrar()">Enviar</button>
      <router-link class="btn orange" to="/login"
        >Já tenho uma conta</router-link
      >
    </span>
  </login-template>
</template>

<script>
import LoginTemplate from "@/templates/LoginTemplate";
import axios from "axios";

export default {
  name: "Cadastro",
  data() {
    return {
      user: {
        name: '',
        email: '',
        password: '',
        password_confirmation: ''
      }

    };
  },
  components: {
    LoginTemplate
  },
  methods: {
    cadastrar() {
      axios
        .post(`http://127.0.0.1:8000/api/usuario/store`, this.user)
        .then(response => {
          console.log(response);
          if (response.data.token) {
            // Login efetuado com sucesso
            console.log("Cadastro efetuado com sucesso");
            sessionStorage.setItem("user", JSON.stringify(response.data));
            this.$router.push("/");
          } else if (response.data.status == false) {
            //Login não existe
            alert("Erro no Cadastro");
          } else {
            // erros de validação
            let erros = "";
            for (let erro of Object.values(response.data)) {
              erros += erro + " ";
            }
            alert(erros);
          }
        })
        .catch(e => {
          //this.errors.push(e)
          alert("Erro! Tente novamente mais tarde!");
        });
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
