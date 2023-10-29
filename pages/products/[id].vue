<template>
  <div>
    <!-- Another way to change meta data -->
    <Head>
      <Title>Nuxt Dojo | {{ product.title }}</Title>
    </Head>
    <ProductDetails :product="product" />
  </div>
</template>

<script setup>
// Destructuring id from vue's useRoute composable; the name (id) needs to match
// the var in our filename ([id].vue)
const { id } = useRoute().params;
const uri = 'https://fakestoreapi.com/products/' + id;

const { data: product } = await useFetch(uri, { key: id });

if (!product.value) {
  // createError is a nuxt function
  throw createError({
    statusCode: 404,
    statusMessage: 'Product not found',
    fatal: true, // catches errors when a server req is not made
  });
}

// a nuxt composable to grab a specific layout
definePageMeta({ layout: 'products' });
</script>

<style lang="scss" scoped></style>
