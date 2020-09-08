<template>
   <div class="row">
      <grid-vue class="input-field" tamanho="12">
        <textarea v-model="conteudo" class="materialize-textarea"></textarea>
        <label>O que está Acontecendo?</label>
      </grid-vue>
      <p>
        <grid-vue v-if="conteudo" tamanho="2 offset-s10" class="btn waves-effect waves-light">Publicar</grid-vue>
      </p>
      {{ conteudo }}
    </div>
</template>

<script>
import GridVue from '@/components/layouts/GridVue'

export default {
  name: 'PublicarConteudoVue',
  props: [
      
  ],
  data () {
    return {
      conteudo: ''
    }
  },
  components: {
    GridVue
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
