<script setup>
import { onBeforeMount, onBeforeUpdate, onMounted, onUpdated, ref } from 'vue';
import NumUpdate from './components/NumUpdate.vue';

onMounted(() => {
    alert(`on mounted : , ${num.value}`)//5
    num.value = 10

})
onBeforeMount(() => {
    alert(`on before mount : , ${num.value}`)
    num.value = 5

})

onBeforeUpdate(() => {
    num.value = num.value > 5 ? 1 : num.value
    alert(`on before update : , ${num.value}`)
})

onUpdated(() => alert(`on updated : , ${num.value}`))

const num = ref(1)
alert(`on created: , ${num.value}`)
const isShow = ref(true)
const unShow = () => isShow.value = false
</script>
 
<template>
    num : {{ num }}
    <button class="border" @click="num++">+</button>
    <NumUpdate :currentNum="num" v-if="isShow" />
    <button class="border" @click="unShow">Not show current num</button>
</template> 
 
<style>
</style>