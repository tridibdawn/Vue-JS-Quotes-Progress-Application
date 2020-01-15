<template>
  <div class="container">
    <app-header :quoteCounts="quotes.length" :maxQuotes="maxQuotes"></app-header>
    <hr>
    <div class="text-center">
      <app-new-quote @quoteAdded="newQuote"></app-new-quote>
    </div>
    <hr>
    <app-quote-grid :quotes="quotes" @quoteDeleted="deleteQuote"></app-quote-grid>
    <div class="row col-xs-12 col-sm-12 col-md-12 col-lg-12">
      <div class="col-xs-12 col-sm-12 col-md-12 col-lg-12 text-center my-4">
        <div class="alert alert-info">Info: Click on a Quote to delete it!</div>
      </div>
    </div>
  </div>
</template>

<script>
import QuoteGrid from './components/QuoteGrid.vue';
import NewQuote from './components/NewQuote.vue';
import Header from './components/Header.vue';

export default {
  data: function() {
    return {
      quotes: [
        'Just a quote to see something!'
      ],
      maxQuotes: 10
    }
  },
  methods: {
    newQuote(quote) {
      if(this.quotes.length >= this.maxQuotes) {
          return alert('Please delete some Quotes to add more Quote!');
      }
      this.quotes.push(quote);
    },
    deleteQuote(index) {
      this.quotes.splice(index, 1);
    }
  },
  components: {
    'app-quote-grid': QuoteGrid,
    'app-new-quote': NewQuote,
    'app-header': Header
  }
}
</script>

<style>

</style>
