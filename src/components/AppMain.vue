<script>

import { store } from '../data/store';
import ProductionCard from './productions/ProductionCard.vue';

export default {
    name: 'AppMain',
    data: () => ({ store }),

    components: { ProductionCard }
}
</script>

<template>

    <ProductionCard></ProductionCard>

</template>

<style lang="scss" scoped>

</style>
