<template>
<div class="row">
<form>
<div class="col-md-6-offset-2 col-lg-4-offset-2 form-group">
<h3>Quote</h3>
<textarea row="3" class="form-control" v-model="quote"></textarea>
</div>
<div class="col-md-6-offset-2">
<button class="btn btn-primary" @click.prevent="addNewQuoteFN">Add Quote</button>
</div>
</form>
</div>
</template>
<script>

export default {
    data:function(){
        return{
            quote:""
        }
    },
 methods:{
     addNewQuoteFN:function(){
      this.$emit('addNewQuote',this.quote);
      this.quote ='';
     }
 }
}
</script>
<style scoped>
.btn{
    margin-bottom:23px;
}
</style>