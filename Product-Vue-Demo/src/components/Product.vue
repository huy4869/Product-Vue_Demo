<template>
  <div id="product">
    <div  class="title">  {{product.title}}</div>
    <div class="">  {{product.description}}</div>
    <div class=""> {{product.tags}}</div>
    <div class=""> {{product.link}}</div>
    <br /> 
  </div>
</template>

<script>
export default {
    
  
  props: {
    product: Object
  },
  
};
</script>

<style lang="scss" scoped>
</style>