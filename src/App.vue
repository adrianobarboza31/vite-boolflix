<template>
  <HeaderComponent/>
  <main>
  <Card/>
  </main>
</template>

<script>
import axios from 'axios';
import Card from './components/Card.vue'
import HeaderComponent from './components/Header.vue'
  export default {
    data(){
      return{
        
      }
    },
    components:{
      Card,
      HeaderComponent
    }
  }
</script>

<style lang="scss" scoped>

</style>