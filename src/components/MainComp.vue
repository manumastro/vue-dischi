<template>
  <main>
      <div id="main-wrapper" class="container"
      v-if="isLoading"
      >
        <div class="row row-cols-1 row-cols-sm-2 row-cols-md-4 row-cols-lg-5 flex-wrap  ">
          <AlbumCards v-for="(album, index) in filteredArray" :key="`album-${index}`"
        :albumItem = album
        />
        </div>
      </div>

      <div class="d-flex justify-content-center"
      v-else>
        <LoadingComponent />
      </div>
      
  </main>
</template>

<script>
import axios from 'axios';

import AlbumCards from './AlbumCards.vue';
import LoadingComponent from './LoadingComponent.vue';

export default {
  components: { AlbumCards, LoadingComponent },
  name: 'MainComp',
  data(){
    return{
      myApi: 'https://flynn.boolean.careers/exercises/api/array/music',
      arrayAlbums: [],
      isLoading: false,
    }
  },
  props:{
    valueToPass: String
  },
  mounted(){
      this.getApi();
  },
  methods: {
    getApi(){
      axios.get(this.myApi)
      .then( r => {
        //console.log(r.data.response);
        this.arrayAlbums = r.data.response;
        this.isLoading = true;
      })
      .catch( e => {
        console.log(e);
      })
    }
  },
  computed:{
    filteredArray(){
      let array = [];
      if(this.valueToPass === ''){
        array = this.arrayAlbums;
      }else{
        array = this.arrayAlbums.filter(album => {
          return album.genre === this.valueToPass;
        })
      }
      return array;
    }
  }
}
</script>

<style lang="scss" scoped>
  main{
    min-height: calc(100vh - 80px);
    background-color: #1e2d3b;
    padding-top: 70px;
  }
</style>