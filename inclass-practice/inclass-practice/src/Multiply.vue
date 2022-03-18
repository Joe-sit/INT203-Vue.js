<script setup>
import { ref } from "@vue/reactivity";
import iconVue from "./icon.vue";


const numbers = new Array(13);

const input = ref(0);
</script>
 
<template>
    <div class="max-w-md py-4 px-8 bg-white shadow-lg rounded-lg my-20">
        <div class="flex justify-center md:justify-end -mt-16"></div>
        <div>
            <h2 class="text-gray-800 text-3xl font-bold text-center">Multiplication table</h2>
            <div class="mt-2 text-gray-600 text-center">
                <input
                    type="number"
                    placeholder="enter a number here"
                    class="border"
                    v-model="input"
                />
                <ul>
                    <li v-for="(number, index) in numbers" :key="index">
                        <span v-if="index !== 0">{{ index }} X {{ input }} = {{ index * input }}</span>
                    </li>
                </ul>
                Input : {{ input }}
            </div>
        </div>
    </div>
</template>
 
<style>

</style>