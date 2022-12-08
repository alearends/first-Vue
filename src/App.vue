<template>
  <Menu />
  <!-- <ul class="container mx-auto gap-6 mt-16 flex flex-wrap"> -->
  <ul class="grid grid-cols-4 container mx-auto gap-6 mt-16">
    <Products v-for="item in items" :prod="prod" :author="authorName" />
  </ul>
</template>

<script setup>
import Menu from "./components/Menu.vue";
import Products from "./components/Products.vue";
import { ref } from "vue";

const items = ref([]);
const authorName = ref("AleArends");

// URL = "https://gateway.marvel.com:443/v1/public/characters?name=flash&ts=1&apikey=0a5566782d241ee50cef64553a6394f2&hash=e34bfaff86a20801ce2e83c783cf6f73";

URL = 'https://api.punkapi.com/v2/beers';


async function getData() {
  const res = await fetch(URL);
  const finalRes = await res.json();

  items.value = finalRes;
  console.log("la estructura es:", items.value);

  // console.log(products.value);
}

getData();

</script>

<style scoped>

</style>