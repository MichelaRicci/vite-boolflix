<script >

import { store } from './data/store.js'
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
export default {
    data() {
        return {
            store,
            moviesUrl: 'https://api.themoviedb.org/3/search/movie?api_key=6f24d8181767396b3077f5017530fcb9&query='
        }
    },
    components: { AppHeader, AppMain },
    methods: {
        filterContents(name) {

            console.log(this.moviesUrl)

        }
    }
}

</script>

<template>

    <AppHeader @search="filterContents"></AppHeader>

    <AppMain></AppMain>



</template>

<style lang="scss">

</style>
