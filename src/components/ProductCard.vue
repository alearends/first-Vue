<template>
  <div class="arrow-up absolute right-96 z-10"></div>
  <section class="bg-white w-96 rounded-md absolute right-96 mt-2 p-2 z-10">
    <div v-for="product in products" v-if="products.length">
      <div class="flex flex-row justify-between items-center py-1">
        <div class="row-1">
          <h2>{{ product.name }}</h2>
          <p>{{ product.ibu }}€</p>
        </div>
        <img :src="product.image_url" class="w-12 h-12 object-cover" alt="{{product.name}}">
      </div>
      <hr />
    </div>
    <div v-else>
      <p>No products in the cart</p>
    </div>
    <div class="flex justify-between items-center mt-5">
      <button class="text-white py-1 px-6 bg-blue-500 rounded">
        View Cart
      </button>
      <p>Total: {{ totalPrice }}€</p>
    </div>
  </section>
</template>
  
<script setup>
import {computed} from "vue";
const props = defineProps(["products"]);

const totalPrice = computed(() => {
  const price = props.products.reduce((acc, curr) => {
    return acc + curr.ibu;
  },0);
  return price;
});
</script>
  
<style scoped>
.arrow-up {
  width: 0;
  height: 0;
  border-left: 20px solid transparent;
  border-right: 20px solid transparent;
  border-bottom: 20px solid white;
  margin-top: -10px;
  margin-right: 50px;
}

</style>