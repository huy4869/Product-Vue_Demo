<template>
  <div class="wrapper-container">
    <side-bar />
    <top />
    <con-tent />

  </div>
</template>

<script>
import SideBar from "./SideBar.vue";
import Top from "./Top.vue";
import ConTent from "./Content.vue";
export default {
  components: {
    SideBar,
    Top,
    ConTent,
  },
};
</script>

<style
NavigationBar lang="scss" scoped>
</style>