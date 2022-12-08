<template>
    <li id="card" class="w-60 rounded mx-auto my-0 flex flex-col items-center ">
        <img class="w-full my-0 mx-auto" :src="item.image_url" :alt="item.name">
        <a class="text-xl mt-5" href="">{{ item.name.length > 10 ? item.name.substring(0, 10) + "..." : item.name }}</a>
        <p class="text-sm">{{ item.description.substring(0, 10) + "..." }}</p>
        <div class="flex flex-row">
            <p class="text-sm text-left">{{item.ibu}} €</p>
            <p class="text-sm text-right">10 x{{(item.ibu.value/10)}} €</p>
        </div>
        {{ author }}
        <ButtonGreen />
    </li>

</template>

<script setup>
import ButtonGreen from './ButtonGreen.vue';
const props = defineProps(["item","author"])

</script>

<style scoped></style>