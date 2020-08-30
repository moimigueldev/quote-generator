<template>
  <div class="container">
    <app-trackbar></app-trackbar>
    <app-textbox></app-textbox>
    <app-quotes class="mt-5"></app-quotes>
    <app-footer></app-footer>
  </div>
</template>

<script>
  import Trackbar from './components/Trackbar'
  import Textbox from './components/Textbox'
  import Quote from './components/Quote'
  import Quotes from './components/Quotes'
  import Footer from './components/Footer'

export default {
  components: {
    appTrackbar: Trackbar,
    appTextbox: Textbox,
    appQuote: Quote,
    appQuotes: Quotes,
    appFooter: Footer
  }
}
</script>

<style lang="scss">

</style>
