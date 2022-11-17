<template>
    <div>
        <h2>film</h2>
        <div class="d-flex" v-for="(value) in filmlist ">
      {{value.original_title}}
      {{value.title}}
      {{value.vote_average}}
      {{value.original_language}}
<div>
    <img :src="imgURL + value.poster_path" alt="">
</div>

    <span v-for="n in 5" class="fa-star" :class="(n <= (Math.ceil(value.vote_average / 2))) ?'fa-solid':'fa-regular'"></span>
      <div v-if="flag.includes(value.original_language)">
        <img :src="'/img/' + value.original_language+'.svg'" alt="">
      </div>
    </div>
    </div>
    
</template>

<script>
    export default {
        props:['filmlist','imgURL'],
        data(){
            return{
                image:'',
                flag:['it','en','es','fr'],
            }
            
        },
    }
</script>

<style lang="scss" scoped>
img{
    width: 50px;
}
</style>