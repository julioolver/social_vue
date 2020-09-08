<template>

  <span>
    <publicar-conteudo-vue />
    <h2>Login</h2>
    
    <card-conteudo-vue perfil="https://materializecss.com/images/yuna.jpg"
    nome = "Julio Cesar" 
    data = "09/07/2020">
      <card-detalhe-vue 
      img="https://materializecss.com/images/sample-1.jpg" 
      titulo="" 
      txt="Este é o texto da postagem, favor informar o que quiser."/>
    </card-conteudo-vue>
  </span>

</template>

<script>
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
    PublicarConteudoVue
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
