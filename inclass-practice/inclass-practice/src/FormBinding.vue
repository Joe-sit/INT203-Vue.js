<script setup>
import { ref } from 'vue';

const comment = ref('');
const favorColor = ref('');
const agree = ref('');
const checkedActivities = ref([]);
const jobSelected = ref('');
const favorPlace = ref([]);
</script>
 
<template>
    <select v-model="favorPlace" multiple>
        <option value="sea">Sea</option>
        <option value="mountain">Mountain</option>
        <option value="museum">Museum</option>
    </select><br>
    <span>Your favorite place: {{ favorPlace }}</span>
</template>
 
<style>
</style>