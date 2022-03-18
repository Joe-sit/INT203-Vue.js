<script setup>
import { computed, ref } from 'vue';
console.clear();
const props = defineProps({
    yourText: {
        type: String,
        require: true
    },
    yourColor: {
        type: String,
        require: true
    }

})

console.log(props);
// props.yourText = "Confirm";

// const buttonText = ref(props.yourText);
// const buttonText = computed(() => props.yourText);
</script>
 
<template>
    <button class="button-color">{{ yourText }}</button>
</template>
 
<style>
.button-color {
    background-color: v-bind(yourColor);
}
</style>
