<template>
    <div class="d-flex align-items-center justify-content-between">
       <h1>boolflix</h1>
       <div class="d-flex form">
            <input type="text" v-model="serchs">
            <button  @click="searc">search</button>
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
}
.form{
    height: 30px;
}
</style>