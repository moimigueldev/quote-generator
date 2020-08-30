<template>

    <div class="row justify-content-center">
        <div class="col-md-3 quotes"  v-for="(quote, index) of quotes" @click="deleteQuote(index)" v-bind:key='index'>
            <p >{{quote}}</p>
        </div>
 
    </div>
</template>

<script>
import {eventBus} from '../main'

    export default {
        data: function () {
            return  {
                quotes: []
            }   
        },
        methods: {
            deleteQuote(index) {
                this.quotes.splice(index, 1);
                eventBus.$emit('deltedQuote', quote)
            }
        },
        created() {
            eventBus.$on('quoteAdded', (quote) => {
                if (this.quotes.length !== 10) {
                    this.quotes.push(quote)
                }
                
            })
        }
        
    }
</script>

<style lang="scss" scoped>
    .row {
        margin-top: 40px;
    }
    .quotes {
        border: 1px solid black;
        overflow-wrap: break-word;
        font-weight: 700;
        margin: 10px;
    font-family: cursive;
    font-size: 20px;
    min-height: 99px;
    max-height: 99px;
    overflow-y: scroll;
    // margin: 5px;
    }
</style>