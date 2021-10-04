<template>
  <section>
    <div class="container">
      <Album
        v-for="(element, index) in filteredGenders"
        :key="index"
        :album_info="element"
      />
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
  props:{
    gender:String,
  },
  data() {
    return {
      albums: [],
    };
  },
  created() {
    axios.get("https://flynn.boolean.careers/exercises/api/array/music").then((answer) => {
        this.albums = answer.data.response;
    });
  },
  computed:{
    filteredGenders(){
      // console.log("gender: " + this.genders);
      // console.log("artists=>"+this.artists);
      const albumFiltered=this.albums.filter((element)=>{
        if(this.gender==""){
          return true;
        }
        return element.genre==this.gender;
      });
      return albumFiltered;
    },
    genders(){
      const calculatedGenders=[];
      this.albums.forEach((element)=>{
        if(!calculatedGenders.includes(element.genre)){
          calculatedGenders.push(element.genre);
        }
      });
      return calculatedGenders;
    },
    artists(){
      const artists=[];
      this.albums.forEach((element)=>{
        if(!artists.includes(element.author)){
          artists.push(element.author);
        }
      });
      return artists;
    }
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
