<template>
  <div id="product">
    <div  class="title">title + {{product.title}}</div>
    <div class="">tag + {{product.title}}</div>
    <div class="">link</div>
    <div class="">description</div>
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