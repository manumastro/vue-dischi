<template>
  <main>
    <AlbumCards v-for="(album, index) in arrayAlbums" :key="`album-${index}`"
    :albumItem = album
    />
  </main>
</template>

<script>
import axios from 'axios';

import AlbumCards from './AlbumCards.vue';

export default {
  components: { AlbumCards },
  name: 'MainComp',
  data(){
    return{
      myApi: 'https://flynn.boolean.careers/exercises/api/array/music',
      arrayAlbums: [],
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
  }
</style>