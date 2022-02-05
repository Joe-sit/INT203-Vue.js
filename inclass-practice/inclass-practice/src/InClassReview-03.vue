<script setup>
//1. function declaration
function printMessage() {
    console.log('Hello, function');
}
printMessage();

//2. function expression
const showMessage = function (msg) {
    console.log(`Hello,${msg}`);
}
showMessage('This is the message from expression');

//3. arrow function expression
const showMessage2 = (msg) => console.log(`Hello, ${msg}`);
showMessage2('Message from arrow function');
</script>
 
<template>
   <div class="max-w-md py-4 px-8 bg-white shadow-lg rounded-lg my-20">
  <div class="flex justify-center md:justify-end -mt-16">
    
  </div>
  <div>
    <h2 class="text-gray-800 text-3xl font-semibold">Title</h2>
    <p class="mt-2 text-gray-600">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Eos saepe excepturi quasi eius repellat nam. Aut, placeat. Laboriosam qui debitis omnis aspernatur quaerat?</p>
  </div>
  
</div>
</template>
 
<style>
</style>