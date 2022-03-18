<script setup>
defineEmits(['updateMe'])
const prop = defineProps({
  buttonName: {
    type: String,
    default: 'OK'
    // require: true
  }
})
// console.log(prop.buttonName)
</script>

<template>
  <!-- for updateMe1,2 -->
  <!-- <button class="button-color" @click="$emit('updateMe',false, 404, 'FAIL')">{{ buttonName }}</button> -->
  <!-- for updateMe3 -->
  <!-- <button class="button-color" @click="$emit('updateMe', [false, 404, 'FAIL'])">{{ buttonName }}</button> -->
  <!-- for update 4,5,6 -->
  <button class="button-color" @click="$emit('updateMe', {status:false, statusCode:404,result:'FAIL'})">{{ buttonName }}</button>
</template>

<style scoped>
.button-color {
  background-color: darkmagenta;
}
</style>