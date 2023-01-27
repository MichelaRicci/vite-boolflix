<script>


export default {

    name: 'AppHeader',

    data() {
        return {
            searching: '',
        }
    },

    components: { Searchbar },

    props: {
        placeholder: String,
        buttonLabel: String

    },

    emits: ['searched', 'submit']


}



</script>

<template>


    <form @submit.prevent="$emit('submit')">
        <input type="text" v-model.trim="searching" @keyup="$emit('searched', searching)"
            :placeholder="placeholder || 'Cerca un titolo...'">
        <button type="submit">{{ buttonLabel || 'Cerca' }}</button>
    </form>


</template>

<style lang="scss" scoped>

</style>
