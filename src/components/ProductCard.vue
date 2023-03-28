<template>
    <div class="product-card">
        <img :src="image" :alt="title" />
        <h3>{{title}}</h3>
    </div>
</template>

<script>
    export default {
        name: "ProductCard",
        props: {
            image: String,
            title: String
        }
    }
</script>

<style lang="scss" scoped>
    .product-card {
        & img {
            width: 100%;
        }
    }
</style>