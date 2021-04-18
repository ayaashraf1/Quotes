<template>
<div class="row">
<appQuote v-for="(quote, index) in quotes" :key="index" @click.native="deleteThisQuote(index)">{{quote}}</appQuote>
</div>
</template>
<script>
import quote from './quote.vue';
export default {
    props:['quotes'],
    components:{
        appQuote:quote
    },
    methods:{
        deleteThisQuote:function(index){
             this.$emit('deleteThis',index);
        }
    }

    
}
</script>
<style>
</style>