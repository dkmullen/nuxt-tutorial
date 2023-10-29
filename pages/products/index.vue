<template>
  <div>
    <h2>Products</h2>
    <div class="grid grid-cols-4 gap-5">
      <div v-for="p in products">
        <!-- <NuxtLink :to="`/products/${p.id}`">{{ p.title }}</NuxtLink> -->
        <ProductCard :product="p" />
      </div>
    </div>
  </div>
</template>

<script setup>
// a nuxt composable to grab a specific layout
definePageMeta({ layout: 'products' });

const { data: products } = await useFetch('https://fakestoreapi.com/products');

// composable to override meta settings which are in nuxt.config.js - see another way in [id].vue
useHead({
  title: 'Nuxt Dojo | Merch',
  meta: [{ name: 'description', content: 'My merch' }],
});
</script>

<style scoped></style>
