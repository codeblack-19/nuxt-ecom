<template>
    <div class="card text-center">
        <img :src="product.image" :alt="product.title" class="thumb">
        <p class="font-bold text-grey-400 m-4 truncate">{{ product.title }}</p>
        <NuxtLink :to="`/products/${product.id}`">
            <p class="btn my-4">View Details</p>
        </NuxtLink>
    </div>
</template>

<script setup lang="ts">
import ProductType from '~/types/productType';

const { product } = defineProps<{
    product: ProductType
}>()

</script>

<style scoped>
    .thumb{
        max-height: 120px;
        max-width: 70%;
        margin: 0 auto;
    }
</style>