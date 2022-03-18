<script setup>
import { computed, ref } from 'vue';
const notes = ref([]);
const newNote = ref('');
const addNote = () => notes.value.push(newNote.value);
const keywords = ref('');
const filterNote = computed(() =>
    notes.value.filter((note) =>
        note.toLowerCase().includes(keywords.value.toLowerCase()))
)
</script>
 
<template>
    <span v-if="notes.length > 0">
        Filter Note:
        <input type="text" class="border" v-model="keywords" />
        <br />
        <ul>
            <li v-for="note in filterNote">{{ note }}</li>
        </ul>
    </span>
    Note Note:
    <input type="text" class="border" v-model="newNote" />
    <button @click="addNote" class="border">Add Note</button>
</template>
 
<style>
body {
    margin: 2%;
}
</style>