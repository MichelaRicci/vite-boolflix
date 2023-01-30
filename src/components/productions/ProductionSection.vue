<script>
import { store } from '../../data/store';

export default {
    name: "ProductionSection",
    props: {
        title: String,
        collection: String
    },

    data() {
        return { store }
    }
}

</script>

<template>
    <section :id="collection">
        <h2>{{ title }}</h2>
        <ProductionCard v-for="production in store[collection]" :key="production.id" :item="production">
        </ProductionCard>


    </section>


</template>


<style lang="scss" scoped>

</style>