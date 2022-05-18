<template>
  <div>
    <select class="mx-4"
        @change="$emit('searchArtist', selectedArtist)"
        v-model="selectedArtist"
        name="artista">
          <option value="">Seleziona un'artista</option>
          <option value="Bon Jovi">Bon Jovi</option>
          <option value="Sting">Sting</option>
          <option value="Queen">Queen</option>
          <option value="Steve Gadd Band">Steve Gadd Band</option>
          <option value="Iron Maiden">Iron Maiden</option>
          <option value="Eric Clapton">Eric Clapton</option>
          <option value="Deep Purple">Deep Purple</option>
          <option value="Metallica">Metallica</option>
          <option value="Dave Weckl">Dave Weckl</option>
          <option value="Michael Jackson">Michael Jackson</option>
      </select>
  </div>
</template>

<script>
export default {
  name: 'SelectArtist',
  data(){
    return{
      selectedArtist: ''
    }
  }
}
</script>

<style lang="scss" scoped>
  select{
    padding: 8px 15px;
    background-color: white;
    border-radius: 5px;
    border: none;
    cursor: pointer;
  }
</style>