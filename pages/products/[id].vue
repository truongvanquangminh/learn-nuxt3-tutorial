<template>
  <div>
    <ProductDetails :product="product"/>
    <div v-if="pending">Loading...</div>
    <div v-if="error">Error loading product.</div>
  </div>
</template>

<script setup>
// Way 1: using route params directly
// const { id } = useRoute().params;
// const uri = "https://fakestoreapi.com/products/" + id;
// Fetch product details from a public API
// const { data: product } = await useFetch(uri, { key: id });

// Way 2: using computed properties
const route = useRoute()
const id = computed(() => route.params.id)
const uri = computed(() => `https://fakestoreapi.com/products/${id.value}`)
// Fetch product details from a public API
const { data: product, pending, error } = await useFetch(uri, {
  key: computed(() => `product-${id.value}`)
})

definePageMeta({
  layout: "products",
});
</script>

<style scoped></style>
