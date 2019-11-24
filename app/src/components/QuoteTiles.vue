<template>
  <div class="row"  @click="onCardDelete">
    <myQuote :key="Quote.id" v-for="(Quote, index) in QuoteText" @click.native="onCardDelete(index)">{{Quote}}</myQuote>
  </div>
</template>
<script>  
import Quote from "../components/Quote";
export default {
    props: ['QuoteText'],
    components: {
      myQuote: Quote
    },
    methods: {
      onCardDelete: function(index){
        this.$emit('clickedItem', index)
      }
    }
}
</script>
<style scoped>

</style>