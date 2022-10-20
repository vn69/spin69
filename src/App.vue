<template>
  <div id="app">
    <header-nav></header-nav>
    <router-view class="layout_body" />
  </div>
</template>

<script>
import "./assets/style/index.scss";

import HeaderNav from "./components/HeaderNav.vue";
export default {
  components: { HeaderNav },
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
.layout_body {
  padding-top: 44px;
}
</style>
