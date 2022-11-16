<template>
    <div class="d-flex" v-for="(value) in filmlist">
      {{value.original_title}}
      {{value.title}}
      {{value.vote_average}}
      {{value.original_language}}
    </div>
</template>

<script>
    export default {
        props:['filmlist']
    }
</script>

<style lang="scss" scoped>

</style>