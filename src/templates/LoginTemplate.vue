<template>
  <span>
    <header>
      <nav-bar logo="Social" url="/" cor="green darken-1">
        <li v-if="!user"><router-link to="/login">Entrar</router-link></li>
        <li v-if="!user"><router-link to="/cadastro">Cadastrar</router-link></li>
        <li v-if="user"><router-link to="/perfil">{{ user.name }}</router-link></li>
        <li v-if="user"><a v-on:click="sair()">Sair</a></li>


      </nav-bar>
    </header>

    <main>
      <div class="container">
        <div class="row">
            <grid-vue tamanho="8">
              <card-menu-vue>
                <slot name="menuesquerdo" />
              </card-menu-vue>
            </grid-vue>
            <grid-vue tamanho="4">
                <slot name="principal" />
            </grid-vue>
        </div>
      </div>
    </main>

    <footer-vue cor="green darken-1" logo="Social" descricao="Teste Desrição" ano="2020">
      <li><a class="grey-text text-lighten-3" href="#!">Home</a></li>
      <li><a class="grey-text text-lighten-3" href="#!">Link 2</a></li>
      <li><a class="grey-text text-lighten-3" href="#!">Link 3</a></li>
      <li><a class="grey-text text-lighten-3" href="#!">Link 4</a></li>
    </footer-vue>

  </span>
</template>

<script>
import NavBar from '@/components/layouts/NavBar'
import FooterVue from '@/components/layouts/FooterVue'
import GridVue from '@/components/layouts/GridVue'
import CardMenuVue from '@/components/layouts/CardMenuVue'


export default {
  name: 'LoginTemplate',
  data() {
    return {
      user : false
    }
  },
  components: {
    NavBar,
    FooterVue,
    GridVue,
    CardMenuVue
  },
  created() {
    console.log('Created');
    let userAux = sessionStorage.getItem('user');
    if(userAux){
      //converte string para json = parse
      this.user = JSON.parse(userAux);
      this.$router.push('/');
    }
  },
  methods: {
    sair(){
      sessionStorage.clear();
      this.user = false
    }
  },
}
</script>

<style>

</style>
