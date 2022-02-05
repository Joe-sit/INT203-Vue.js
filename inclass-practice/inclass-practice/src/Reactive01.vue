<script setup>
import { reactive, ref, toRef, toRefs } from 'vue';
console.clear();
//const counter = ref(1);
//setTimeout(()=> console.log(++counter), 3000);
//setInterval(() => console.log(++counter.value), 3000);

// const student = reactive({std_id: 1234,std_name: 'Joe'});
// console.log(student);
// console.log(student.std_id);

// const drink = reactive(['pepsi','beer','coke']);
// console.log(drink);
// console.log(drink[1]);
// const ids = ref([111,121,131,142]);
// console.log(ids.value);
// console.log(ids.value[2]);

// const idsMoreThan120 = ids.value.filter((id) => id > 120);

// console.log(idsMoreThan120);

const PC = reactive({
    name: 'Gaming-set',
    price: 35000,
    installment: true,
    weight: 15,
    promotion: 20
});
const price = toRef(PC, 'price');
console.log(price.value);

const promotion = toRef(PC, 'promotion');
const intervalId = setInterval(() => console.log(--promotion.value), 1000);
const stopInterval = () => clearInterval(intervalId);
console.log(PC.name);

const { weight, installment } = toRefs(PC);
console.log(weight.value);
console.log(installment.value);

function notification() {
    alert('จะหมดเวลาแล้วนะ');
};

</script>
<template>
    <div id="main-section">
        <p>PC name: {{ PC.name }}</p>
        <p>PC price: {{ price }}</p>
        <p>ผ่อนชำระ : {{ installment }}</p>
        <p>PC weight: {{ weight }}</p>
        <p>Promotion 50%: เหลือ {{ promotion }} วินาที</p>
        <div v-if="PC.promotion == 10">{{ notification() }}</div>
        <button
            @click="stopInterval"
            class="bg-transparent hover:bg-blue-500 text-blue-700 font-semibold hover:text-white py-2 px-4 border border-blue-500 hover:border-transparent rounded"
        >Stop countdown</button>
    </div>

    <!-- <p>Student: {{ student }}</p>
    <p>Student ID: {{student.std_id}}</p>
    <p>All Drink: {{drink}}</p>
    <p>Drink[1] : {{drink[1]}}</p>-->
</template>
<style>
#main-section {
    margin: 20px;
}
</style>