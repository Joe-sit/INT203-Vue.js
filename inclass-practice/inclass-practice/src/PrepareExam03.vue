<script setup>
import { reactive, ref, toRef, toRefs } from 'vue';
// const number = ref([1, 2, 3, 4, 5, 6, 7, 8, 9, 10]);
// console.log(number.value);
// console.log(number.value[4]);
// const evenNumberOnly = number.value.filter((num) => num % 2 == 0);
// console.log("This is even number only : " + evenNumberOnly);

// const toDoList = reactive({ item: 1, task: 'Shopping', priority: 5 });
// console.log(toDoList.item);

// console.clear();
// const PC = reactive({
//     name: 'Gaming-set',
//     price: 35000,
//     installment: true,
//     weight: 15
// });

// const price = toRef(PC, 'price');
// console.log(price.value);

// console.log(PC.name);

// const { weight, installment } = toRefs(PC);
// console.log(weight.value);
// console.log(installment.value);




</script>
 
<template>
    
    <!-- <h2>
        #{{ toDoList.item }}
        {{ toDoList.task }}
        priority: {{ toDoList.priority }}
    </h2>-->
    <!-- <p>PC name: {{ PC.name }}</p>
    <p>PC price: {{ price + 5000 }}</p>
    <p v-if="installment == true">ผ่อนชำระ : ผ่อนชำระได้</p>
    <p v-else>ผ่อนชำระไม่ได้</p>
    <p>PC weight: {{ weight }}</p>-->
</template>
 
<style>
</style>