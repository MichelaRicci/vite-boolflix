<script>

import { store } from '../../data/store';
import { api, poster } from '../../data/index';


export default {
    name: 'ProductionCard',
    data: () => ({ store, api, poster }),

    props: {
        production: Object
    },

    computed: {
        hasFlag() {
            const flags = ['it', 'en'];
            return flags.includes(this.production.original_language);
        },

        srcFlags() {
            const url = new URL(`../../assets/img/${this.production.original_language}.png`, import.meta.url);
            return url.href;
        },

        posterUrl() {
            let posterUrl = "";
            if (this.production.poster_path) {
                posterUrl = poster + this.production.poster_path;
            }
            return posterUrl;

        },

        vote() {
            return Math.floor(this.production.vote_average / 2);
        }


    }
}



</script>

<template>

    <ul>
        <li>{{ production.original_title }}</li>
        <li>{{ production.title }} </li>
        <li>
            <img v-if="hasFlag" :src="srcFlags" :alt="production.original_language">
            <div v-else>{{ production.original_language }}</div>
        </li>
        <li>{{ production.vote_average }}</li>
        <li>
            <i v-for="n in 5" :class="n <= this.vote ? 'fa-solid' : 'fa-regular'" class="fa-star"></i>
        </li>
        <li><img :src="posterUrl" :alt="production.original_name"></li>
    </ul>
</template>

<style lang="scss" scoped>

</style>