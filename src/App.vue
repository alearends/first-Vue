<template>
  <header>
    <nav class="bg-neutral-800 h-5 w-full">
      <ul>
        <li><a href="">AllProducts</a></li>
        <li><a href="">Smartphones</a></li>
        <li><a href="">Notebooks</a></li>
      </ul>
      <button class="bg-blue-400 h-5 flex ">
        Cart
        <img class="cart" src="../image/cart-white.png" alt="Cart Icon">
      </button>
    </nav>
  </header>
<main>
  <article>
    <h1>PROYECTO ALTERNATIVO</h1>
    <div>
      <img src="{{productLink}}" alt="{{productName}}">
      <h2>{{productName}}</h2>
      <div>
        <span>{{productPrice}}</span>
        <span>{{productEasyPaid}}</span>
      </div>
      <button>Add to cart</button>
    </div>
    
  </article>
</main>
</template>

<script setup>
import {ref} from "vue";

</script>

<style scoped>


nav{
  height: 70px;
  box-sizing: border-box;
  padding: 0.5em;
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  color: white;
}

ul {
    width: 30%;
    line-height: 1.15;
    display: flex;
    flex-direction: row;
    justify-content: space-evenly;
    align-items: center;
    flex-wrap: nowrap;
}

button{
  width: 123px;
  height: 36px;
}

.cart{
  width: 22px;
  margin-left: 2%;

}

.flex {
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
}
</style>