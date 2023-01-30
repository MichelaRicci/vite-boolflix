<script >

import axios from 'axios';
import { store } from './data/store.js';
import { api } from './data/index.js';

import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';

import ProductionCard from './components/productions/ProductionCard.vue';

export default {

    name: 'Boolflix',

    data() {
        return {
            store,
            api,
            term: '',
        }
    },

    components: { AppHeader, AppMain, ProductionCard },

    computed: {
        parameters() {
            return {
                params: {
                    language: api.language,
                    api_key: api.key,
                    query: this.term
                }
            }
        }
    },

    methods: {
        newTerm(searched) {
            this.term = searched
        },
        searchProduction() {
            if (!this.term) {
                store.movies = []
            }
            axios.get(`${api.baseUri}/search/movie`, this.parameters)
                .then(res => {
                    store.movies = res.data.results
                })
        }
    }
}

</script>

<template>

    <AppHeader @searched="newTerm" @submit="searchProduction"></AppHeader>


    <AppMain></AppMain>



</template>

<style lang="scss">

</style>
