<template>
    <div>
        <h1 class="header">Quotes Added</h1>
        <div class="progress">
  <div class="progress-bar" role="progressbar" v-bind:style="{'width': progress + '%'}"  aria-valuenow="25" aria-valuemin="0" aria-valuemax="100">{{progress / 10}} / 10</div>
</div>
    </div>
</template>

<script>
import {eventBus} from '../main'
    export default {
        data: function () {
            return {
            progress: 0
            }
        },
        created() {

            

            eventBus.$on('quoteAdded', (quote) => {
                if (this.progress === 100) {
                    alert('Max number of quotes has been reached')
                } else {
                    this.progress = this.progress + 10
                }
                // this.progress = this.progress === 100 ?  : this.progress + 10;
                // // this.progress = 
            })
            eventBus.$on('deltedQuote', (quote) => {
                this.progress = this.progress - 10
            })
        }
    }
</script>

<style lang="scss" scoped>
    .header {
        font-weight: 700;
    }

</style>