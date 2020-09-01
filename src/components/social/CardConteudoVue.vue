<template>
<div class="card">
  <div class="card-content">
    <span class="card-title">Card Title</span>
    <div class="row valign-wrapper">
        <grid-vue tamanho="2">
          <img src="https://materializecss.com/images/yuna.jpg" alt="" class="circle responsive-img"> <!-- notice the "circle" class -->
        </grid-vue>
        <grid-vue tamanho="10">
          <span class="black-text">
            <strong>Maria Silva</strong> - <small>09/07/202 17:45</small>
          </span>
        </grid-vue>
      </div>
  </div>
</div>
</template>

<script>
import GridVue from '@/components/layouts/GridVue'

export default {
  name: 'CardConteudoVue',
  props: [
      
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
