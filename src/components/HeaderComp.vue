<template>
  <header class="d-flex justify-content-between">
    <div id="logo" class="d-flex align-items-center px-3">
      <img src="../assets/img/spotify-logo.png" alt="">
    </div>
    <div id="select-item" class="d-flex align-items-center px-3">
      <select name="genere" id="">
        <option value="">Seleziona un genere</option>
      </select>
    </div>
  </header>
</template>

<script>
export default {
  name: 'HeaderComp'
}
</script>

<style lang="scss" scoped>
  header{
    height: 80px;
    background-color: #2e3a46;
    #logo{
      height: 100%;
      img{
        height: 50px;
      }
    }
    #select-item{
      height: 100%;
      select{
        padding: 8px 15px;
      }
    }
  }
</style>