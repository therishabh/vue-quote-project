<template>
  <div class="row">
    <div class="col-sm-12">
      <h3>Quotes Added</h3>
      <div class="progress">
        <div class="progress">
          <div class="progress-bar" role="progressbar" :style="{width: (savedQuote * 10) + '%'}"> {{savedQuote}} / {{maxQuote}}</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    maxQuote: {
      type: Number
    },
    savedQuote: {
      type: Number
    }
  }
};
</script>

<style scoped>
</style>
