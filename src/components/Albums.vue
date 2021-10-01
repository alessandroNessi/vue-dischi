<template>
  <div>
    <Album />    
  </div>
</template>

<script>
// import axios from "axios",
import Album from "../components/Album.vue";
export default {
  name: "Albums",
  components: {
    Album,
  },
};
</script>

<style lang="scss" scoped>
@import "../assets/style/common.scss";
</style>