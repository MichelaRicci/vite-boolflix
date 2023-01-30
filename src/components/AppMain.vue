<script>

// import { store } from '../data/store';
// import ProductionCard from './productions/ProductionCard.vue';
import ProductionSection from './productions/ProductionSection.vue'


export default {
    name: 'AppMain',

    components: { ProductionSection }
}
</script>

<template>

    <ProductionSection collection="movies" title="Movies"></ProductionSection>

    <ProductionSection collection="series" title="Tv Series"></ProductionSection>
    <!-- 
    <ProductionCard></ProductionCard> -->

</template>

<style lang="scss" scoped>

</style>
