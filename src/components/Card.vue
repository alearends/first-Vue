<template>
  <!-- ini Construcción Card (tarjeta del Producto) -->
  <div id="card" class="flex flex-col">
    <img :src="beer.image_url" class="w-full h-[250px] object-cover" alt="{{beer.name}}">
    <h3 class="text-xl mt-5">{{beer.name.length > 15 ? beer.name.substring(0,15) + "..." : beer.name}}</h3>
    <p class="text-sm">{{beer.description.substring(0, 15) + "..."}}</p>
    <p class="mt-2">{{beer.ibu}}€</p>
    <!-- fin Construcción Card (tarjeta del Producto) -->
    
    <!-- boton para añadir producto al carrito -->
    <!-- la construcción del boton se hizo en Button.vue -->
    <ButtonGreen :text="'Add to cart'" @addToCart = "addToCart" />
  </div>
</template>

<script setup>
// la construcción del boton se hizo en Button.vue
import ButtonGreen from './ButtonGreen.vue';

// los datos del API vienen desde el Padre (App.vue)
const props = defineProps(["beer"]);

// Solicitud del Hijo al Padre para añadir un producto: se define la solicitud y se asigna a una Const
const emits = defineEmits(["addProduct"]);
// Funcion para generar "solicitud al Padre"
function addToCart(){
  emits("addProduct", props.beer);
}

</script>

<style scoped></style>