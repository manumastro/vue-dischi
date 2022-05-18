<template>
  <div>
    <HeaderComp
    @searchArtist="seeArtist" 
    @search="seeValue"/>
    <MainComp
    :artistToPass = artistToPass
    :valueToPass = valueToPass />
  </div>
</template>

<script>
import HeaderComp from './components/HeaderComp.vue'
import MainComp from './components/MainComp.vue'

export default {
  name: 'App',
  data(){
    return{
      valueToPass: '',
      artistToPass: '',
    }
  },
  components: {
    HeaderComp,
    MainComp,
  },
  methods:{
    seeValue(value){
      this.valueToPass = value;
    },
    seeArtist(artist){
      this.artistToPass = artist;
    }
  }
}
</script>

<style lang="scss">
@import './assets/style/_general.scss';

</style>
