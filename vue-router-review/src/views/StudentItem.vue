<script setup>
import { useRoute, useRouter } from 'vue-router';
const { params } = useRoute()
console.log(params.studentId);

const myRouter = useRouter()
const goBack = () => myRouter.go(-1)
const goToMyPortfolio = () => myRouter.push({ name: 'MyPortfolio' })
</script>
 
<template>
    <div>
        <h1 class="font-bold">Student's Item</h1>
        <p>Your selected student is {{ this.$route.params.studentId }}</p>
        <button class="border mx-2" @click="goBack">Back</button>
        <button class="border" @click="goToMyPortfolio">My Portfolio</button>
    </div>
</template>
 
<style>
</style>