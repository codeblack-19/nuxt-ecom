<template>
    <div>
        <ProductDetails :product="product" />
    </div>
</template>

<script setup lang="ts">
import ProductType from '~/types/productType';

const { id } = useRoute().params
const uri = 'https://fakestoreapi.com/products/' + id

definePageMeta({
    layouts: 'products'
})

// fetch the product
const { data: product } = await useFetch<ProductType>(uri)

</script>

<style scoped>

</style>