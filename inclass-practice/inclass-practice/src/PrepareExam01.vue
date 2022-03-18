<script setup>
// const fullSyn = 2;
// const shortSyn = 3;
// const msg = "Hello guys";

// const boldText = "font-weight : bold;";
// const thinText = "font-weight : thin;";

// const standardImgSize = "width: 50px; height:50px;";
// const imgPath = "../public/images/cpunotworking.png";

// const paraStyle = "<b><i>Komi can't communicate</b></i>";
// const contextStyle = "<em> Rating: 9/10 </em>";
// const isSearch = true;
// const userName = '';
// console.log(Boolean(userName));
// const weight = 78;
// const height = 1.75;
// const result = weight/Math.pow(height,2);+
const depositAmt = 60000;
//const interest = 0.1;
const name = '';
</script>
 
<template>
    <!-- <p v-text="fullSyn"></p> -->
    <!-- <p>{{ shortSyn + 5 }}</p>
    <p>{{ msg.toLowerCase() }}</p>
    <h2 v-bind:style ="boldText">This is full syntax.</h2>
    <h2 :style="thinText">This is short syntax.</h2>
    <img src="./assets/logo.png" alt="logo" :style="standardImgSize">
    <img :src="imgPath" alt="Images from server" :style="standardImgSize">-->
    <!-- <p v-html="paraStyle"></p>
    <p v-html="contextStyle"></p>-->
    <!-- <div v-show="isSearch">
        <label for="search">Search </label>
        <input type="text" id="search" class="border"/>
    </div>-->
    <!-- <p v-show="userName">Hello, {{ userName  }}</p> -->
    <!-- <p>Weight: {{ weight }}</p>
    <p>Height: {{ height }}</p>
    <p>Result: {{ result  }}</p>
    <hr>
    <p v-if="result >= 30">"อ้วนมาก"</p>
    <p v-else-if="result >= 25 && result <= 29.9">"อ้วน"</p>
    <p v-else-if="result >= 18.6 && result <= 24">"ปกติ"</p>
    <p v-else>"ผอมมาก"</p>-->
    <p>Deposit Amount: {{ depositAmt }}</p>
    <p v-if="depositAmt < 10000">Interest : 0</p>
    <p v-else-if="depositAmt <= 49999">Interest: {{ depositAmt*0.1 }}</p>
    <p v-else-if="depositAmt <= 99999">Interest: {{ depositAmt * 0.2 }}</p>
    <p v-else>Interest: {{ depositAmt * 0.25 }}</p>
    <p v-show="name">Hello, {{ name }}</p>
</template>
 
<style>
</style>