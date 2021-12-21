<template>
  <div id="app">
    <wrapper-container/>
  </div>
</template>

<script>
import WrapperContainer from './components/WrapperContainer.vue'

export default {
  name: 'App',
  components: {
    WrapperContainer
  }
}
</script>

<style>
#app {
  position: absolute;
  top: 0px;
  left: 0px;
  width: 1440px;
  height: 900px;         
  background: #FFFFFF;
}
</style>
