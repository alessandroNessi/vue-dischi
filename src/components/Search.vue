<template>
  <nav>
    <!-- document.getElementById('gender__filter').value -->
    <select name="gender__filter" id="gender__filter" @change="$emit('filteredGender',$event.target.value)">
      <option value="">Tutti i generi</option>
      <option v-for="(element, index) in this.genders" :key="index" :value="element">{{element}}</option>
    </select>
    <!-- <select name="artist__filter" id="album__filter">
      <option value="">Tutti gli album</option>
      <option>
    </select> -->
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
    artists: Array,
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
