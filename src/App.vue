<script >

import axios from 'axios';
import { store } from './data/store.js';
import { api } from './data/';
import Searchbar from './components/Searchbar.vue';
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
export default {

    name: 'Boolflix',

    data() {
        return {
            store,
            api
        }
    },

    components: { AppHeader, AppMain, Searchbar },
}

</script>

<template>

    <AppHeader></AppHeader>


    <AppMain></AppMain>



</template>

<style lang="scss">

</style>
