<template>
  <div class="row">
    <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
      <label>Quote</label>
      <textarea class="form-control" rows="3" v-model="newQuote"></textarea>
    </div>
    <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
      <button class="btn btn-primary" @click="addNewQuote">Add Quote</button>
    </div>
  </div>
</template>

<script>
export default {
  props : {
    addQuote : {
      type : Function
    }
  },
  data : function() {
    return {
      newQuote : ""
    }
  },
  methods : {
    addNewQuote() {
      this.$emit('addQuote', this.newQuote);
      this.newQuote = '';
    }
  }
}
</script>
