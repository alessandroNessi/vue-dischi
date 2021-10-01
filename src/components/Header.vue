<template>
  <div class="headerContainer">
    <img
      src="../assets/img/spotify-logo.png"
      :style="`height:${headerHeight}`"
      alt="logo"
    />
  </div>
</template>

<script>
export default {
  name: "Header",
  props: ["headerHeight"],
};
</script>

<style lang="scss" scoped>
@import "../assets/style/common.scss";
.headerContainer {
  padding: 0.625rem;
  background-color: $bg_header_color;
  img {
    height: 100%;
  }
}
</style>
