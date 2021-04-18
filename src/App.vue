<template>
  <div class="container">
  <progressApp :counter="quotes.length" :maxCounter="maxQuotes"></progressApp>
  <appNewQuote @addNewQuote="addQuote"></appNewQuote>
  <appQuoteGrid :quotes="quotes" @deleteThis="deleteQuote"></appQuoteGrid>
  <div class="row">
  <div class="col-md-12 col-lg-12 text-center">
  <div class="alert alert-info">Info:Click On Quote to delete it!!</div>
  </div>
  </div>
  </div>
</template>

<script>
import quoteGrid from './components/quotesGrid.vue';
import newQuote from './components/newQuote.vue';
import header from './components/header.vue';

export default {
 data: function(){
   return {
     quotes:['just a quote to see something'],
     maxQuotes:10
   }
 },
 components:{
   appQuoteGrid:quoteGrid,
   appNewQuote:newQuote,
   progressApp:header
 },
 methods:{
   addQuote:function(quote){
        if(this.quotes.length >= this.maxQuotes){
        alert("maximum number of quotes,delete some quotes first");
      }
      else{
      this.quotes.push(quote);
      }
   
   },
   deleteQuote:function(quote){
       this.quotes.splice(quote,1);
   }
 }
}
</script>

<style scoped>
span{
  border:1px solid red;
}
</style>
