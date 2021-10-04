<template>
  <nav>
    <select name="gender__filter" id="gender__filter" @change="$emit('filteredGender',$event.target.value)">
      <option value="">Tutti i generi</option>
      <option v-for="(element, index) in this.genders" :key="index" :value="element">{{element}}</option>
    </select>
    <select name="artist__filter" id="album__filter" @change="$emit('filteredArtists',$event.target.value)">
      <option value="">Tutti gli artisti</option>
      <option v-for="(element, index) in this.artists" :key="index" :value="element">{{element}}</option>
    </select>
  </nav>
</template>

<script>
export default {
  name: "Search",
  data(){
      return{
      }
  },
  props:{
    artists: [],
    genders: [],
  }
};
</script>

<style scoped lang="scss">
@import "../assets/style/common.scss";
nav{
  height: 4rem;
  padding: 0.5rem 2rem;
  background-color: $bg-header-color;
  select{
    margin-right: 5rem;
  }
}
</style>
