<template>
  <section>
    <div class="container">
      <Album v-for="(elm, index) in albums" :key="index" :album_info=elm />
    </div>
  </section>
</template>

<script>
import axios from "axios";
import Album from "../components/Album.vue";
export default {
  name: "Albums",
  components: {
    Album,
  },
  data(){
      return{
          albums:[],
      }
  },
  created(){
      axios.get("https://flynn.boolean.careers/exercises/api/array/music").then((answer)=>{
          this.albums=answer.data.response;
          console.log(this.albums);
      });
  }
};
</script>

<style lang="scss" scoped>
@import "../assets/style/common.scss";
section {
  background-color: $bg_body_color;
  height: calc(100vh - 4.5rem);
}
.container {
  margin: auto;
  display: flex;
  flex-wrap: wrap;
  padding-top: 3rem;
  max-width: 87.5rem;
}
</style>
