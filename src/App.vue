<template>
  <div id="app">
    <Header :headerHeight="'3rem'" />
    <Search @filteredArtists="artist__filter" @filteredGender="gender__filter" :artists="this.compiledArtists" :genders="this.compiledGenres"/>
    <p></p>
    <Albums @getArtists="populate_artists" @getGenres="populate_genres" :artist="this.artist" :gender="this.genere"/>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Albums from "./components/Albums.vue";
import Search from "./components/Search.vue"

export default {
  name: "App",
  components: {
    Header,
    Albums,
    Search,
  },
  data(){
    return{
      artist:'',
      genere:'',
      compiledGenres: [],
      compiledArtists: [],
    }
  },
  methods:{
    gender__filter(str){
      this.genere=str;
    },
    artist__filter(str){
      console.log(str);
      this.artist=str;
    },
    populate_genres(array){
      this.compiledGenres=array;
    },
    populate_artists(array){
      this.compiledArtists=array;
    }
  },
};
</script>

<style lang="scss">
@import "./assets/style/common.scss";
</style>
