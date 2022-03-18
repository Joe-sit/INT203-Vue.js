<script setup>
const accounts = [{
    name: 'salary',
    amount: 10000
},
{
    name: 'rent',
    amount: -2500
},
{
    name: 'parking fee',
    amount: 0
}, {
    name: 'car fuel',
    amount: -600
}, {
    name: 'commission',
    amount: 5500
},
]
const sumAmount = accounts.map(item => item.amount).reduce((prev, curr) => prev + curr, 0);
const green = 'color:white; background-color:green';
const red = 'color:white; background-color:red';

</script>
 
<template>
    <ul>
        <li v-for="account in accounts">
            {{ account.name }}
            <span v-if="account.amount > 0" :style="green">{{ account.amount }}</span>
            <span v-if="account.amount < 0" :style="red">{{ account.amount }}</span>
        </li>
    </ul>
    <p>Net Totol: {{ sumAmount }}</p>
</template>
 
<style>
</style>