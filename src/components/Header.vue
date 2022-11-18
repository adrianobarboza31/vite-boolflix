<template>
    <div class="d-flex align-items-center justify-content-between cc">
       <h1 class="pt-3 ps-3">boolflix</h1>
       <div class="d-flex form justify-content-end pe-4">
            <input type="text" v-model="serchs" placeholder="titoli, persone e generi">
            <button class="fa-solid fa-search" style="font-size:15px ;"  @click="searc"></button>
       </div>
    </div>
</template>

<script>
    export default {
      
        methods:{
            searc(){
                this.$emit('getfilm',this.serchs)
            }
        },
        data(){
            return{
                serchs:''
            }
        }
           }
</script>

<style lang="scss" scoped>
h1{
    color: red;
    text-transform: uppercase;
    font-family: 'Open Sans', sans-serif;
    font-size: 35px;
}
input{
    width: 180px;
    height: 25px;
    color: white;
    background-color: black;
    border: 1px solid white;
}
button{
    height: 23px;
    background-color:#141414 ;
    color: white;
    border: 0px solid black;
}
.cc{
    background-color:#141414 ;
    font-size: 10px;
}
.form{

}
</style>