<script setup>
import { ref } from 'vue';
const base = ref(4);
const height = ref(8);
let result = ref(0);
const calculateArea = () => {
    result.value = (1 / 2 * base.value * height.value);
    console.log(result.value);
};
</script>
 
<template>
    <div class="max-w-md py-4 px-8 bg-white shadow-lg rounded-lg my-20" id="main">
        <div class="flex justify-center md:justify-end -mt-16"></div>
        <div>
            <h2 class="text-gray-800 text-xl font-semibold">Area Calculator</h2>
            <p>Base: {{ base }}</p>
            <p>Height: {{ height }}</p>
            <p>Area Result: {{ result }}</p>
            <button
                @click="base++"
                class="bg-transparent hover:bg-blue-500 text-blue-700 font-semibold hover:text-white px-4 py-0.5 border border-blue-500 hover:border-transparent rounded m-1"
            >Add base</button>
            <br />
            <button
                @click="height++"
                class="bg-transparent hover:bg-blue-500 text-blue-700 font-semibold hover:text-white px-4 py-0.5 border border-blue-500 hover:border-transparent rounded m-1"
            >Add height</button>
            <br />
            <button
                @click="calculateArea"
                class="bg-transparent hover:bg-green-500 text-green-700 font-semibold hover:text-white px-4 py-0.5 border border-green-500 hover:border-transparent rounded m-1"
            >Compute area</button>
        </div>
    </div>
</template>
 
<style>
#main {
    margin: 40%;
    width: 20%;
}
</style>