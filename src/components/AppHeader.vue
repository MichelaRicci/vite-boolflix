<script>

export default {

    name: 'AppHeader'
}

</script>

<template>

    <input type="text" v-model.trim="searching" @keyup.enter="$emit('search', searching)"
        placeholder="Cerca un titolo...">
    <button>Cerca</button>

</template>

<style lang="scss" scoped>

</style>
