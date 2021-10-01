<template>
  <section >
    <div class="container">
      <Album />
      <Album />
      <Album />
      <Album />
      <Album />
      <Album />
      <Album />
      <Album />
      <Album />
      <Album />
    </div>
  </section>
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
section {
  background-color: $bg_body_color;
  height: calc( 100vh - 4.5rem);
}
.container {
  margin:  auto;
  display: flex;
  flex-wrap: wrap;
  padding-top: 3rem;
  max-width: 87.5rem;
}
</style>
