<script setup>
import { ref } from 'vue'
const randNumbers = ref([])
// generates random number in range (1-99)
const generateNumber = () => {
    let duplicate = false
    const rand = Math.floor(Math.random() * 99 + 1)
    duplicate = randNumbers.value.some((randNumber) => randNumber === rand)
    duplicate ? generateNumber() : randNumbers.value.push(rand)
    console.log("Numer is generated!");
    console.log(rand);
}

const buttons = [];
buttons.length = 9;
const buttonText = 'font-size:10px';
const myId = '<b><i>63130500091,Pattarapon Makhirun</b></i>';

const addNumber = () => {
    var lastElement = randNumbers.value[randNumbers.value.length - 1];
    buttons.push(lastElement);
    console.log(lastElement);
    console.log(buttons);
};

// buttons.push(randNumbers.value.length - 1);
</script>

<template>
    <div class="top-container">
        <h2 v-html="myId"></h2>
        <div class="action-button">
            <button class="border" @click="generateNumber">Generate New Number</button>
            <button class="border">Reset</button>
        </div>
        <div class="error-message">
            <!-- show error message when a user adding the same number in the bingo sheet -->
        </div>
        <div class="grid-container">
            <div class="grid-item" v-for="(button, index) in buttons" :key="index">
                <button
                    v-if="randNumbers.length == 0"
                    :style="buttonText"
                    class="bg-blue-500 text-white font-bold py-2 px-4 rounded opacity-50 cursor-not-allowed"
                    @click="addNumber"
                >Add Number</button>
                <button
                    v-if="randNumbers.length > 0"
                    :style="buttonText"
                    class="bg-blue-500 text-white font-bold py-2 px-4 rounded"
                    @click="addNumber"
                >Add Number</button>
            </div>
        </div>
        <div class="generate-number">
            <!-- show the list of generated number here -->
            <ul>
                <!-- <span v-if="randNumbers.length > 0">Something is added</span> -->
                <li
                    v-for="(randNumber, index) in randNumbers"
                    :key="index"
                >Generate Number#{{ index + 1 }}: '{{ randNumber }}'</li>
            </ul>
        </div>
    </div>
</template>

<style scoped>
.top-container {
    width: 330px;
}
.action-button {
    padding: 10px;
    display: flex;
    gap: 5px;
}
.grid-container {
    display: grid;
    grid-template-columns: 100px 100px 100px;
    grid-template-rows: 80px 80px 80px;
    column-gap: 5px;
    row-gap: 5px;
    background-color: green;
    padding: 10px;
}
.grid-item {
    display: flex;
    background-color: rgba(255, 255, 255, 0.8);
    border: 1px solid rgba(0, 0, 0, 0.8);
    font-size: 30px;
    text-align: center;
    justify-content: center;
    align-items: center;
    cursor: pointer;
}
.generate-number {
    font-size: 20px;
}
.error-message {
    height: 40px;
    color: red;
}
</style>
