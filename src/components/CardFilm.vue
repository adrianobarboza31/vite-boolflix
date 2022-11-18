<template >
    <div class="bo pt-3">
        <h2 class="ps-3">film</h2>
    
    
    <div class="d-flex cc ">
    <div class="ab-card d-flex ps-2" v-for="(value) in filmlist ">
        <div class="at-card">
            <div class="card-front card-block">
                <img :src="value.poster_path? imgURL + value.poster_path:'https://via.placeholder.com/342x500'" alt="">
            </div>
            <div class="card-back card-block">
            <div class="pt-4 ps-3">
                <strong>
                    Titolo:
                </strong>
                {{value.title}}
            </div>
            <div class="ps-3">
                <strong>Titolo originale:</strong>
                {{value.original_title}}
            </div>
            <div class="ps-3">
                <strong>
                    Voto:
                </strong>
               
                <span v-for="n in 5" class="fa-star" :class="(n <= (Math.ceil(value.vote_average / 2))) ?'fa-solid':'fa-regular'"></span>
                <!-- {{value.vote_average}} -->
            </div>
           <div class="ps-3">
             <strong>Lingua:</strong>
            <span  v-if="flag.includes(value.original_language)">
                <img :src="'/img/' + value.original_language+'.svg'" alt="">
            </span>
            </div>
            <div class="ps-3 pe-3 pt-1">
              <strong>Overview:</strong>  {{value.overview}} 
            </div>
        </div>
        
        </div>
     
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
    width: 100%;
    height: 468px;
}
div.card-back img{
    width: 40px;
    height: 20px;
}
.ab-card{
color: white;
}
.at-card{
    // overflow-x: scroll;
    // position: relative;
    // width: 450px;
   height: 500px;
    // background-color:#141414;
    // transform-style: preserve-3d;
    // transition: transform 1s;
    position: relative;
    width: 330px;
    margin: 0 10px;
    transform-style: preserve-3d;
    transition: transform 1s;
}
.bo{
    background-color:#141414;
}
h2{
    color: white;
    font-size: 25px;
    text-transform: uppercase;
    font-family: 'PT Sans', sans-serif;;
}
.cc{
    overflow-x: auto;
}
div.text-center{
    padding-top: 5px;
    padding-bottom: 5px;
}
.card-front{
    // background-color: gray;
   height: 468px;
   position: absolute;
   width: 100%;
   backface-visibility: hidden;
}
.card-back{
    backface-visibility: hidden;
    position: absolute;
    height: 468px;
    background-color: black;
    width: 100%;
//    background-color: black;
//     color: white;
    transform:rotateY(180deg) ;
    color: #C3C3C3;
}
.card-block{
//     position: absolute;
   
//    width: 100%;
//    display: flex;
// backface-visibility:hidden;
}
.at-card:hover {
    transform: rotateY(180deg);
}
strong{
    color: white;
}
</style>