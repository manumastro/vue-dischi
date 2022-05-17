<template>
  <main>
      <div id="main-wrapper" class="container d-flex flex-wrap justify-content-between"
      v-if="isLoading"
      >
        <AlbumCards v-for="(album, index) in arrayAlbums" :key="`album-${index}`"
        :albumItem = album
        />
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
      isLoading: false
    }
  },
  mounted(){
      this.getApi();
  },
  methods: {
    getApi(){
      axios.get(this.myApi)
      .then( r => {
        console.log(r.data.response);
        this.arrayAlbums = r.data.response;
        this.isLoading = true;
      })
      .catch( e => {
        console.log(e);
      })
    }
  },
}
</script>

<style lang="scss" scoped>
  main{
    min-height: calc(100vh - 80px);
    background-color: #1e2d3b;
    padding-top: 70px;
  }
</style>