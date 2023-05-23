<template>
    <div>
        <Head>
            <Title>Nuxt Ecom | {{ product?.title }}</Title>
            <Meta name="description" :content="product?.description" />
        </Head>
        <ProductDetails :product="product" />
    </div>
</template>

<script setup lang="ts">
import ProductType from '~/types/productType';

const { id } = useRoute().params
const uri = 'https://fakestoreapi.com/products/' + id

definePageMeta({
    layout: 'products'
})

// fetch the product
const { data: product } = await useFetch<ProductType>(uri)

if(!product.value){
    throw createError({
        statusCode: 404,
        statusMessage: 'Product Not found',
        fatal: true
    })
}

</script>

<style scoped>

</style>