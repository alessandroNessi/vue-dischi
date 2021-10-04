<template>
  <section>
    <div class="container">
      <Album v-for="(element, index) in filteredByAll" :key="index" :album_info="element"/>
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
    artist:String,
  },
  data() {
    return {
      albums: [],
      albumsFilt: [],
      genres: [],
      artists: [],
    };
  },
  created() {
    axios.get("https://flynn.boolean.careers/exercises/api/array/music").then((answer) => {
        this.albums = answer.data.response;
        this.albums.forEach((element)=>{
          if(!this.genres.includes(element.genre)){
            this.genres.push(element.genre);
          }
        });
        this.albums.forEach((element)=>{
          if(!this.artists.includes(element.author)){
            this.artists.push(element.author);
          }
        });
        this.$emit('getGenres',this.genres);
        this.$emit('getArtists',this.artists);
    });
  },
  computed:{
    filteredByAll(){
      console.log(this.artist);
      const albumFiltered=this.albums.filter((element)=>{
        if(this.gender==""||this.gender==element.genre){
          if(this.artist==""){
            return true;
          }
          return element.author==this.artist;
        }else{
          return false;
        }
        // return element.genre==this.gender;
      });
      return albumFiltered;
    },
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
