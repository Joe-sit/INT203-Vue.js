<script setup>
const warningColor = 'orange'
const successText = 'color:green'
const warningText = 'color:orange'
const italicText = 'italic'
const isError = false
</script>
<template>
  <!-- style attribute with object syntax -->
  <p :style="{ color: warningColor, 'font-style': italicText }">
    this is style with object syntax
  </p>
  <p :style="isError ? 'color:red' : 'color:green'">this is error message</p>
  <p :style="isError ? successText : warningText">this is binding on varible</p>
  
</template>
<style></style>