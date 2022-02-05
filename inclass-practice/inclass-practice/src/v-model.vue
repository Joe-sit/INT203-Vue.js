<script setup>
import { ref, computed } from 'vue';
const base = ref(4);
const height = ref(8);
const result = computed(() => (1 / 2) * base.value * height.value);

</script>
 
<template>
    <h2>Area Calculator</h2>
    <p>Base: {{ base }}</p>
    <input type="number" v-model="base">
    <p>Height: {{ height }}</p>
    <input type="number" v-model="height">
    <p>Area Result: {{ result }}</p>
</template>
 
<style>
body{
    background-color: aliceblue;
}
</style>