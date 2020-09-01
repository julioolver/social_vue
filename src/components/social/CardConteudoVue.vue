<template>
<div class="card">
  <div class="card-content">
    <span class="card-title">Card Title</span>
    <div class="row valign-wrapper">
        <grid-vue tamanho="2">
          <img :src="perfil" :alt="nome" class="circle responsive-img"> <!-- notice the "circle" class -->
        </grid-vue>
        <grid-vue tamanho="10">
          <span class="black-text">
            <strong>{{nome}}</strong> - <small>{{ data }}</small>
          </span>
        </grid-vue>
      </div>
      <slot />

      <div class="card-action">
        <i class="material-icons">favorite_border</i>
        <i class="material-icons">insert_comment</i>
      </div>
  </div>
</div>
</template>

<script>
import GridVue from '@/components/layouts/GridVue'

export default {
  name: 'CardConteudoVue',
  props: [
      'perfil',
      'nome',
      'data'
  ],
  data () {
    return {
     
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
