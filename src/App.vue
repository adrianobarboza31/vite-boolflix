<template>
  <HeaderComponent  @getfilm="getfilm"/>
  <main>
  <Card :filmlist="filmlist"/>
  </main>
</template>

<script>
import axios from 'axios';
import Card from './components/Card.vue'
import HeaderComponent from './components/Header.vue'

  export default {
    data(){
      return{
        filmURL:"https://api.themoviedb.org/3/search/movie?api_key=e99307154c6dfb0b4750f6603256716d&query=",
        seriestvURL:"https://api.themoviedb.org/3/search/tv?api_key=e99307154c6dfb0b4750f6603256716d&query=",
        search:'',
        filmlist:[],
        seriestvlist:[]
      }
    },
    components:{
      Card,
      HeaderComponent
    },
    methods:{
      getfilm(value){
        axios.get(this.filmURL + value).then(
          (res)=>{
            this.filmlist=[...res.data.results];
            console.log(this.filmlist)
          },
          )
      },
      getseries(){
        axios.get(this.seriestvURL+ this.search).then(
          (res)=>{
            this.seriestvlist=[...res.data.results];
            console.log(this.seriestvlist)
          },
          )
      }
    }
  }
</script>

<style lang="scss" scoped>

</style>