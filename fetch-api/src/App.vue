<script setup>
import { ref, onBeforeMount } from 'vue'
import NoteList from './components/NoteList.vue'
import CreateEditNoteVue from './components/CreateEditNote.vue';
const notes = ref([])
// GET
const getNotes = async () => {
  const res = await fetch('http://localhost:5000/notes')
  if (res.status === 200) {
    notes.value = await res.json()
    console.log(notes.value)
  } else console.log('error, cannot get notes')
}
onBeforeMount(async () => {
  await getNotes()
})
//DELETE
const removeNote = async (removeNoteId) => {
  const res = await fetch(`http://localhost:5000/notes/${removeNoteId}`, {
    method: 'DELETE'
  })
  if (res.status === 200) {
    notes.value = notes.value.filter((note) => note.id !== removeNoteId)
    console.log('deleted successfullly')
  } else console.log('error, cannot delete')
}

//CREATE
const createNewNote = async (newNoteDetail) => {
  // console.log(newNote)
  const res = await fetch('http://localhost:5000/notes', {
    method: 'POST',
    headers: {
      'content-type': 'application/json'
    },
    body: JSON.stringify({
      noteDetail: newNoteDetail
    })
  })
  if (res.status === 201) {
    const addedNote = await res.json()
    notes.value.push(addedNote)
    console.log('added successfully')
  } else {
    console.log('error, cannot add')
  }
}
</script>
<template>
  <div>
    <CreateEditNoteVue @createNote="createNewNote" />
    <NoteList :noteList="notes" @deleteNote="removeNote" @editNote="toEditingMode" />
  </div>
</template>
<style></style>