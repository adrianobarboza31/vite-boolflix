<template>
    <div>
    <h2>serietv</h2>
    <div class="d-flex" v-for="(value) in seriestvlist">
        {{value.original_name}}
      {{value.name}}
      <div>
    <img :src="imgURL + value.poster_path" alt="">
</div>
      {{value.vote_average}}
      {{value.original_language}}
      <div v-if="flag.includes(value.original_language)">
        <img :src="'/img/' + value.original_language+'.svg'" alt="">
      </div>
      <span v-for="n in 5" class="fa-star" :class="(n <= (Math.ceil(value.vote_average / 2))) ?'fa-solid':'fa-regular'"></span>
    </div>
    </div>
    
</template>

<script>
    export default {
        props:['seriestvlist','imgURL'],
        data(){
            return{
                image:'',
                flag:['it','en','es','fr']
            }
            
        },
        
    }
</script>

<style lang="scss" scoped>
img{
    width: 50px;
}
</style>