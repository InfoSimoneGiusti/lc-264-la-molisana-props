<template>
    <div class="products">

        <div v-for="(pasta, index) in formatiPasta" class="box" :key="index">
            <ProductCard :image="pasta.src" :title="pasta.titolo"/>
        </div>

    </div>
</template>


<script>
    import ProductCard from './ProductCard.vue'

    export default {
        name: 'ProductList',
        components: {
            ProductCard
        },
        props: {
            formatiPasta: Array
        }
    }
</script>


<style scoped lang="scss">
    .products {
        max-width: 1000px;
        margin: auto;

        display: flex;
        flex-wrap: wrap;

        & .box {
            width: calc(100% / 3);
        }
    }
</style>