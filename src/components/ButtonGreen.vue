<template>
    <button class="bg-green-400 h-10 w-full rounded text-center text-white py-1 px-6 mt-3 flex flex-row">
        {{ text }}
        <img class="h-5" src="../assets/image/cart-white.png" alt="Cart Icon">
    </button>
</template>

<script setup>
const props = defineProps(["text"]);

</script>

<style scoped></style>