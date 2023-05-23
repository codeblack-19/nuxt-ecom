<template>
    <div>
        <div class="grid grid-cols-4 gap-5">
            <div v-for="p in products">
                <ProductCard :product="p" />
            </div>
        </div> 
    </div>
</template>

<script setup lang="ts">
import ProductType from '~/types/productType';

definePageMeta({
    layout: "products",
})

const { data: products } = await useFetch<[ProductType]>('https://fakestoreapi.com/products')

useHead({
    title: 'Nuxt Ecom | Merch',
    meta: [
        {name: 'description', content: 'Nuxt 3 Merch Store'}
    ]
})
</script>

<style scoped>

</style>