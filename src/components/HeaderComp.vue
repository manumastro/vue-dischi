<template>
  <header class="d-flex justify-content-between">
    <div id="logo" class="d-flex align-items-center px-4">
      <a href="#"><i class="fa-brands fa-spotify"></i></a>
    </div>
    <div id="select-item" class="d-flex align-items-center px-4">
      <SelectGenre @search="seeValue" />
      <SelectArtist @searchArtist="seeArtist"/>
    </div>
  </header>
</template>

<script>
import SelectGenre from './SelectGenre.vue'
import SelectArtist from './SelectArtist.vue';

export default {
  components: { SelectGenre, SelectArtist },
  name: 'HeaderComp',
  methods:{
    seeValue(value){
      this.$emit('search', value);
    },
    seeArtist(artist){
      console.log(artist);
      this.$emit('searchArtist', artist);
    }
  }
}
</script>

<style lang="scss" scoped>
  header{
    height: 80px;
    background-color: #2e3a46;
    #logo{
      height: 100%;
      a{
        color: green;
        i{
          font-size: 50px;
        }
      }
    }
    #select-item{
      height: 100%;
      
    }
  }
</style>