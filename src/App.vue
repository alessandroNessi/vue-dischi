<template>
  <div id="app">
    <Header :headerHeight="'3rem'" />
    <Albums :headerHeight="'3rem'" />
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Albums from "./components/Albums.vue";

export default {
  name: "App",
  components: {
    Header,
    Albums,
  },
};
</script>

<style lang="scss">
@import "./assets/style/common.scss";
</style>
