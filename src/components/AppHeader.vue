<script>

import Searchbar from './Searchbar.vue';


export default {

    name: 'AppHeader',

    components: { Searchbar },

    emits: ['searched', 'submit']



}



</script>

<template>
    <Searchbar @searched="$emit('searched', $event)" @submit="$emit('submit', $event)"></Searchbar>


</template>

<style lang="scss" scoped>

</style>
