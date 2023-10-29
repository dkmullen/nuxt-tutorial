<template>
  <div>
    <h2>About</h2>
    <p>
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Nam minima dolor
      eius deleniti hic eveniet. Dolor quasi quaerat quo amet!
    </p>
    <p>
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Nam minima dolor
      eius deleniti hic eveniet. Dolor quasi quaerat quo amet!
    </p>
    <div>{{ data2.data }}</div>
    <div>{{ data }}</div>
  </div>
</template>

<script setup>
const data2 = await useFetch('/api/ninja?name=Dennis', {
  method: 'post',
  body: { age: 59 },
});
const { data } = await useFetch('/api/currency/GBP');
</script>

<style scoped>
h2 {
  margin-bottom: 20px;
  font-size: 36px;
}
p {
  margin: 20px 0;
}
</style>
