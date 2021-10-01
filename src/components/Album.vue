<template>
  <div class="album">
    <img class="album__image" :src="album_info.poster" alt="" />
    <h3 class="album__title">{{album_info.title}}</h3>
    <p class="album__info">{{album_info.author}}</p>
    <p class="album__info">{{album_info.year}}</p>
  </div>
</template>

<script>
export default {
  name: "Album",
  data(){
      return{
          data:[],
      }
  },
    props:["album_info"],
};
</script>

<style scoped lang="scss">
@import "../assets/style/common.scss";
.album {
  text-align: center;
  width: calc(20% - 40px);
  margin: 10px 20px;
  background-color: $bg_header_color;
  padding: 10px;
  &__title {
    margin:10px 0 20px 0;
    color: white;
  }
  &__info {
    color: rgba($color: #ffffff, $alpha: 0.3);
  }
  &__image{
      width: 100%;
  }
}
</style>
