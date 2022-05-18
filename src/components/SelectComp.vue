<template>
  <div>
    <select
    @change="$emit('search', selectedValue)"
    v-model="selectedValue"
    name="genere">
      <option value="null">Seleziona un genere</option>
      <option value="rock">Rock</option>
      <option value="pop">Pop</option>
      <option value="metal">Metal</option>
      <option value="jazz">Jazz</option>
  </select>
  </div>
</template>

<script>
export default {
  name: 'SelectComp',
  data(){
    return{
      selectedValue: ''
    }
  },
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