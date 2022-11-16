<template>
    <div>
        <h2>film</h2>
        <div class="d-flex" v-for="(value) in filmlist">
      {{value.original_title}}
      {{value.title}}
      {{value.vote_average}}
      {{value.original_language}}
      <img v-if="value.original_language=='it'"  src='../assets/img/it.svg' alt="">
      <img v-if="value.original_language=='en'"  src='../assets/img/gb-eng.svg' alt="">
      <img v-if="value.original_language=='es'"  src='../assets/img/es.svg' alt="">
      <img v-if="value.original_language=='fr'"  src='../assets/img/re.svg' alt="">
    </div>
    <h2>serietv</h2>
    <div class="d-flex" v-for="(value) in seriestvlist">
        {{value.original_name}}
      {{value.name}}
      {{value.vote_average}}
      {{value.original_language}}
      <img v-if="value.original_language=='it'"  src='../assets/img/it.svg' alt="">
      <img v-if="value.original_language=='en'"  src='../assets/img/gb-eng.svg' alt="">
      <img v-if="value.original_language=='es'"  src='../assets/img/es.svg' alt="">
      <img v-if="value.original_language=='fr'"  src='../assets/img/re.svg' alt="">
    </div>
    </div>
    
</template>

<script>
    export default {
        props:['filmlist','seriestvlist'],
        data(){
            return{
                image:''
            }
            
        },
        methods:{
            
        }
    }
</script>

<style lang="scss" scoped>
img{
    width: 50px;
}
</style>