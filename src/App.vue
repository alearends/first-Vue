<template>
<Overlay v-if="show" @click="showElement" />
<header class="bg-neutral-700 text-white p-5 flex justify-center items-center relative">
  <a href="#" class="mx-9">AllProducts</a>
  <a href="#" class="mx-9">Smartphones</a>
  <a href="#" class="mx-9">Notebooks</a>
  <button @click="showElement" class="py-1 px-6 ml-28 bg-blue-500 rounded">
    Cart <span class="bg-white rounded-full text-black count" v-if="cartProducts.length">{{cartProducts.length}}</span></button>
</header>
<ProductCard v-if="show" :products="cartProducts" />
<section class="grid grid-cols-4 container mx-auto gap-6 mt-16">
  <Card v-for="beer in beers" :beer="beer" @add-product="addToCart"/>
</section>
</template>


<script setup>
import Card from './components/Card.vue';
import Overlay from './components/Overlay.vue';
import ProductCard from './components/ProductCard.vue';
import {ref} from "vue";
const beers = ref([]);
const show = ref(false);
const cartProducts = ref([]);
// URL="https://api.punkapi.com/v2/beers";

async function getBeer(){
  const res = await fetch("https://api.punkapi.com/v2/beers");
  const finalRes = await res.json();
  // console.log("hey!!", finalRes);

  beers.value = finalRes;
}
getBeer();

function showElement(){
  show.value = !show.value;
}

function addToCart(e){
  cartProducts.value.push(e);
}

</script>

<style scoped>
.count {
  padding: 0 6px;
}
</style>