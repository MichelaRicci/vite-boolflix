<script>
import { store } from '../../data/store';
import ProductionCard from './ProductionCard.vue';

export default {
    name: "ProductionSection",
    props: {
        title: String,
        collection: String
    },

    components: { ProductionCard },

    data() {
        return { store }
    }
}

</script>

<template>
    <section :id="collection">
        <h2>{{ title }}</h2>
        <ProductionCard v-for="productions in store[collection]" :key="productions.id" :item="productions">
        </ProductionCard>
    </section>


</template>


<style lang="scss" scoped>

</style>