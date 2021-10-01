<template>
  <div class="album">
      <img class="album__image" src="" alt="">
      <h3 class="album__title">cippa</h3>
      <p class="album__info">lippa</p>
      <p class="album__info">lippone</p>
  </div>
</template>

<script>
export default {
  name: "Album",
};
</script>

<style scoped lang="scss">
@import '../assets/style/common.scss';
    .album{
        text-align: center;
        width: calc(20% - 40px);
        margin: 10px 20px;
        background-color: $bg_header_color;
        padding: 10px;
        &__title{
            margin-bottom: 20px;
            color: white;
        }
        &__info{
            color: rgba($color: #ffffff, $alpha: 0.3);
        }
    }
</style>
