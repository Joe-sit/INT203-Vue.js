<script setup>
import { ref } from "@vue/reactivity";
import { computed } from "@vue/runtime-core";

const base = ref(4);
const height = ref(8);
const result = ref(0);
const calculateArea = computed(() => (1 / 2) * base.value * height.value);

</script>
 
<template>
    <h1>Area Calculator</h1>
    <!-- <p>{{ base }}</p>
    <p>{{ height }}</p>-->
    <input type="number" v-model="base" class="border" />
    <input type="number" v-model="height" class="border" />
    <button @click="base++">[add base]</button>
    <button @click="height++">[add height]</button>
    <p>{{ calculateArea }}</p>
</template>
 
<style>
</style>