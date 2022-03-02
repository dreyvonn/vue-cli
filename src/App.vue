<template>
    <div class="container">
        <div class="row">
            <div class="col-xs-12">
               <app-quote></app-quote>
               <h2>The Quote</h2>
               <p>A Wonderful Quote</p>
            </div>
        </div>
    </div>
</template>

<script>
    import Quote from './components/Quote.vue';

    export default {
        components: {
            appQuote: Quote
        }
    }
</script>

<style>
</style>
