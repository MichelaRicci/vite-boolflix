<script>

import { store } from '../../data/store';



export default {
    name: 'ProductionCard',
    data: () => ({ store }),

    props: {
        content: Object
    },


    computed: {
        title() {
            return this.content.title || this.content.name
        },

        originalTitle() {
            return this.content.original_title || this.content.original_name
        },

        hasFlag() {
            const flag = ['it', 'en']
            return flag.includes(this.content.original_language)
        },

        flagSrc() {
            const url = URL(`../../assets/img/${this.content.original_language}.png`, import.meta.url);
            return url.href
        },

    }

}

</script>

<template>

    <ul v-for="movie in store.movies">
        <li>{{ movie.original_title }}</li>
        <li>{{ movie.title }} </li>
        <li> {{ movie.original_language }}</li>
        <li>{{ movie.vote_average }}</li>
    </ul>
</template>

<style lang="scss" scoped>

</style>