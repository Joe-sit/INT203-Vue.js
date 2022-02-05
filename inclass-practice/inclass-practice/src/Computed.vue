<script setup>
import { ref, computed } from 'vue';
const base = ref(4);
const height = ref(8);
const result = computed(() => (1 / 2) * base.value * height.value);

</script>
 
<template>
    <h2>Area Calculator</h2>
    <p>Base: {{ base }}</p>
    <p>Height: {{ height }}</p>
    <p>Area Result: {{ result }}</p>
    <button @click="base++">Add base</button>
    <br />
    <button @click="height++">Add height</button>
</template>
 
<style>
</style>