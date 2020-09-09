<template>

  <login-template>
    <span slot="menuesquerdo">
      <img src="https://cakeerp.com/wp-content/uploads/2019/10/capa-2-1080x675.png" class="responsive-img">
    </span>
    <span slot="principal">
      <h2>Login</h2>

      <input type="text" placeholder="E-mail" value="">
      <input type="text" placeholder="Senha" value="">
      <button type="button" class="btn">Entrar</button>
    </span>
    
  </login-template>

</template>

<script>
import LoginTemplate from '@/templates/LoginTemplate'
import CardConteudoVue from '@/components/social/CardConteudoVue'
import CardDetalheVue from '@/components/social/CardDetalheVue'
import PublicarConteudoVue from '@/components/social/PublicarConteudoVue'

export default {
  name: 'Login',
  data () {
    return {
      
    }
  },
  components: {
    CardConteudoVue,
    CardDetalheVue,
    PublicarConteudoVue,
    LoginTemplate
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
