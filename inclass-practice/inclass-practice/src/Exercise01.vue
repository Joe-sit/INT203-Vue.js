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
  name: 'parking free',
  amount: 0
},
{
  name: 'car fuel',
  amount: -600
},
{
  name: 'commission',
  amount: 5500
},
{
  name: 'upgrade CPU',
  amount: -8000
},
{ name: 'ตีกะหรี่',
  amount: -2500
}
 
]
const listStyle = 'list-style:none;';
const sumAmount = accounts.map(item => item.amount).reduce((prev, curr) => prev + curr, 0);
const green = 'background-color: #A5C879; border-radius: 0.3rem;';
const red = 'background-color: #DC4C4C; border-radius: 0.3rem;';
const hide = 'display:hidden;';
</script>
 
<template>
  <div class="center">
    <h1 class="uppercase text-5xl font-bold">My account</h1>
    <ul class="list-acc" v-bind:style="listStyle">
      <li
        class="list-account shadow-lg text-xl"
        v-for="(value, propKey, index) in accounts"
        :key="index"
      >
        <p v-if="value.amount != 0">
          <span class="bold-txt">Name:</span>
          {{ value.name }}
        </p>
        <p>
          <span class="bold-txt" v-if="value.amount != 0">Amount:</span>
          <span v-if="value.amount > 0" v-bind:style="green">{{ value.amount }}</span>
          <span v-else-if="value.amount < 0" v-bind:style="red">{{ value.amount }}</span>
        </p>
      </li>
      <p class="net-totol">
        <span class="bold-txt">Net Totol:</span>
        {{ sumAmount }}
      </p>
    </ul>
  </div>
</template>
 
<style>
.bold-txt {
  font-weight: bold;
}
.list-account {
  background-color: white;
  margin: 25px 0 25px 0;
  border-radius: 0.5rem;
  width: auto;
  padding-left: 5px;
}
.center {
  margin: auto;
  width: 50%;
  padding: 10px;
}
.net-totol {
  display: inline-block;
  width: 100%;
  padding-left: 50%;
  font-size: large;
}
</style>