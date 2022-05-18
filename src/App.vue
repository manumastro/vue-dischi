<template>
  <div>
    <HeaderComp @search="seeValue"/>
    <MainComp :valueToPass = valueToPass />
  </div>
</template>

<script>
import HeaderComp from './components/HeaderComp.vue'
import MainComp from './components/MainComp.vue'

export default {
  name: 'App',
  data(){
    return{
      valueToPass: ''
    }
  },
  components: {
    HeaderComp,
    MainComp,
  },
  methods:{
    seeValue(value){
      this.valueToPass = value;
    }
  }
}
</script>

<style lang="scss">
@import './assets/style/_general.scss';

</style>
