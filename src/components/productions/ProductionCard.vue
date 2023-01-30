<script>

import { store } from '../../data/store';
import { api } from '../../data/index';


export default {
    name: 'ProductionCard',
    data: () => ({ store, api }),

    props: {
        productions: Object
    },

    computed: {
        hasFlag() {
            const flags = ['it', 'en'];
            return flags.includes(this.productions.original_language);
        },

        srcFlags() {
            const url = new URL(`../../assets/img/${this.productions.original_language}.png`, import.meta.url);
            return url.href;
        },

        posterUrl() {
            let posterUrl = "";
            if (this.prod.poster_path) {
                posterUrl = poster + this.productions.poster_path;
            }
            return posterUrl;

        },

        vote() {
            return Math.floor(this.prod.vote_average / 2);
        }


    }
}



</script>

<template>

    <ul v-for="productions in store.movies">
        <li>{{ productions.original_title }}</li>
        <li>{{ productions.title }} </li>
        <li>
            <img v-if="hasFlag" :src="srcFlags" :alt="productions.original_language">
            <div v-else>{{ productions.original_language }}</div>
        </li>
        <li>{{ productions.vote_average }}</li>
        <li>
            <i v-for="n in 5" :class="n <= this.vote ? 'fa-solid' : 'fa-regular'" class="fa-star"></i>
        </li>
        <li><img :src="posterUrl" :alt="productions.original_name"></li>
    </ul>
</template>

<style lang="scss" scoped>

</style>