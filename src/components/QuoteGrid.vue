<template>
    <div class="row col-xs-12 col-sm-12 col-md-12 col-lg-12">
        <app-quote v-for="(quote, index) in quotes" @click.native="deleteQuote(index)">{{ quote }}</app-quote>
    </div>
</template>

<script>
import Quote from './Quote.vue';

export default {
    props: ['quotes'],
    methods: {
        deleteQuote(index) {
            this.$emit('quoteDeleted', index);
        }
    },
    components: {
        'app-quote': Quote
    }
}
</script>

<style scoped>

</style>