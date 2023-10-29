<template>
  <div>
    <header class="shadow-sm bg-white">
      <nav class="container mx-auto p-4 flex justify-between">
        <NuxtLink to="/" class="font-bold">Nuxt Tutorial</NuxtLink>
        <ul class="flex gap-4">
          <li>
            <!-- Nuxtlink is built in; causes app to nav like spa; also adds 
              active class to active link -->
            <NuxtLink to="/">Home</NuxtLink>
          </li>
          <li><NuxtLink to="/about">About</NuxtLink></li>
          <li><NuxtLink to="/products" class="btn">Products</NuxtLink></li>
          <li>
            <NuxtLink to="/products/abc" class="btn">Fake Products</NuxtLink>
          </li>
        </ul>
      </nav>
    </header>
    <!-- output page component -->
    <div class="container mx-auto p-4">
      <slot />
    </div>
  </div>
</template>

<style scoped>
.router-link-exact-active {
  color: green;
}
</style>
