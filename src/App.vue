<template>
  <div class="container">
    <Header></Header>
    <ProgressBar :maxQuote="maxQuote" :savedQuote="quotes.length"></ProgressBar>
    <!-- <progress-bar ></progress-bar> -->
    <new-quote @addQuote="addNewQuote($event)"></new-quote>
    <quote-list :quotes="quotes" @delete="quoteDelete($event)"></quote-list>
    <div class="row">
      <div class="col-sm-12 text-center">
        <div class="alert alert-info">Info: Click on a Quote to delete it!</div>
      </div>
    </div>
    <Footer></Footer>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Footer from "./components/Footer.vue";
import ProgressBar from "./components/Quote/ProgressBar.vue";
import NewQuote from './components/Quote/NewQuote.vue';
import QuoteList from './components/Quote/QuoteList.vue';

export default {
  data: function() {
    return {
      maxQuote : 10,
      quotes : ['First Quote'],
    }
  },
  components: {
    Header,
    Footer,
    ProgressBar,
    NewQuote,
    QuoteList
  },
  methods : {
    addNewQuote(newQoute) {
      if(this.quotes.length >= this.maxQuote){
        alert('you can not enter more than 10 quotes')
        return false;
      }
      this.quotes.push(newQoute);
    },
    quoteDelete(indexNo){
      this.quotes.splice(indexNo, 1);
    }
  }
};
</script>

<style>
</style>
