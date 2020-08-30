<template>
  <div class="quote-container">
    <div class="row  justify-content-center">
      <div class="col-md-6 col-md-offset-3 text-center  " >

          <div class="form-group ">
            <label for="exampleFormControlTextarea1">Quote</label>
            <textarea class="form-control" v-model="message" id="quote" rows="3"></textarea>
          </div>
          <button  @click="submitQuote" class="btn text-center mx-auto btn-lg btn-primary">Add Quote</button>

      </div>
    </div>
  </div>
</template>

<script>
    import {eventBus} from '../main'
export default {
  data: function () {
    return {
      message:
        "At w3schools.com you will learn how to make a website. They offer free tutorials in all web development technologies.",
    };
  },
  methods: {
    submitQuote() {
      eventBus.$emit('quoteAdded', this.message)
      this.message = ''
    },
  },
};
</script>

<style lang="scss" scoped>

</style>
