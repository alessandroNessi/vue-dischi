<template>
  <div id="app">
    <Header :headerHeight="'3rem'" />
    <Search @filteredGender="gender__filter" :artists="'cippa'" :genders="['Pop','Rock','Jazz']"/>
    <p></p>
    <Albums :gender="this.genere"/>
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
      genere:'',
    }
  },
  methods:{
    gender__filter(str){
      console.log(str);
      this.genere=str;
      console.log(this.genere);
    }
  },
  // computed:{
  //   gender__filter(gender){
  //     return gender;
  //   }
  // }
};
</script>

<style lang="scss">
@import "./assets/style/common.scss";
</style>
