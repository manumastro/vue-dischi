<template>
  <div class="col album-card d-flex flex-column ">
    <img :src="albumItem.poster" :alt="albumItem.title">
    <h4 class="pt-3">{{albumItem.title}}</h4>
    <span class="pt-2"> {{albumItem.author}}</span>
    <span class="year">{{albumItem.year}}</span>
  </div>
</template>

<script>
export default {
  name: 'AlbumCards',
  props: {
    albumItem: Object,
  }
}
</script>

<style lang="scss" scoped>
  .album-card{
    padding: 18px 18px 36px 18px;
    margin-bottom: 20px;
    background-color: #2e3a46;
    border: 15px solid #1e2d3b;
    img{
      width: 100%;
    }
    h4{
      text-transform: uppercase;
      color: whitesmoke;
      text-align: center;
      font-size: 16px;
      font-weight: bold;
    }
    span{
      color: #7a7675;
      display: block;
      font-size: 22px;
      font-weight: 600;
      text-align: center;
      &.year{
        font-size: 16px;
        font-weight: 600;
      }
    }
  }
</style>