<template>
  <ul>
    <li
      v-for="(item, index) in quotes"
      :key="item + Math.floor((Math.random() * 1000))"
      @click="deleteQuote(index)"
    >
      <quote-grid>{{item}}</quote-grid>
    </li>
  </ul>
</template>

<script>
import QuoteGrid from "./QuoteGrid.vue";
export default {
  props: {
    quotes: {
      type: Array
    },
    delete : {
      type : Function
    }
  },
  components: {
    QuoteGrid
  },
  methods : {
    deleteQuote(index) {
      this.$emit('delete', index);
    }
  }
};
</script>
<style scoped>
ul li {
  list-style-type: none;
  padding: 0;
  margin: 0;
}
</style>

