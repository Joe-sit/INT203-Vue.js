<script setup>
import { ref } from 'vue'
const newNote = ref('')
defineEmits(['createNote'])

</script>
 
<template>
    <div>
        <h2>Create/Edit Note</h2>Note Detail:
        <input type="text" v-model="newNote" />
        <button @click="$emit('createNote', newNote)">Create</button>
    </div>
</template>
 
<style>
</style>