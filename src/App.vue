<template>
  <HeaderComponent  @getfilm="getfilm"/>
  <main>
    <CardFilm :filmlist="filmlist" :imgURL="imgURL"/>
  <Card  :seriestvlist="seriestvlist" :imgURL="imgURL"/>
  </main>
</template>

<script>
import axios from 'axios';
import Card from './components/CardTv.vue'
import CardFilm from './components/CardFilm.vue';
import HeaderComponent from './components/Header.vue'

  export default {
    data(){
      return{
        filmURL:"https://api.themoviedb.org/3/search/movie?api_key=e99307154c6dfb0b4750f6603256716d&query=",
        seriestvURL:"https://api.themoviedb.org/3/search/tv?api_key=e99307154c6dfb0b4750f6603256716d&query=",
        search:'',
        imgURL:'https://image.tmdb.org/t/p/w342',
        filmlist:[],
        seriestvlist:[]
      }
    },
    components:{
      Card,
      HeaderComponent,
      CardFilm
    },
    methods:{
      getfilm(value){
       
        axios.get(this.filmURL + value).then(
          (res)=>{
            this.filmlist=[...res.data.results];
           
            console.log(this.filmlist)
            axios.get(this.seriestvURL+ value).then(
          (res)=>{
            this.seriestvlist=[...res.data.results];
            console.log(this.seriestvlist)
          },
          )
          },
          )
      },
     
    }
  }
</script>

<style lang="scss" scoped>

</style>