<template>
<span>
  <!-- //https://materializecss.com/images/sample-1.jpg -->
  <div v-if="img" class="card-image">
    <img :src="img">
    <span class="card-title">{{ titulo || '' }}</span>
  </div>

  <div v-if="txt" class="card-content">
    <p>{{txt}}</p>
  </div>
</span>
</template>

<script>
import GridVue from '@/components/layouts/GridVue'

export default {
  name: 'CardDetalheVue',
  props: [
    'img',
    'titulo',
    'txt'
  ],
  data () {
    return {
     
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
