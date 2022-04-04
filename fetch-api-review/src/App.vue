<script setup>
import { onBeforeMount, ref } from 'vue'
import NoteList from './components/NoteList.vue';
import CreateEditNote from './components/CreateEditNote.vue';
const notes = ref([])


//GET METHOD
const getNotes = async () => {
    const res = await fetch('http://localhost:5000/notes')
    if (res.status === 200) {
        notes.value = await res.json()
        console.log(notes.value);
    } else
        console.log('error, connot get notes');
}

onBeforeMount(async () => {
    await getNotes()
})

//DELETE METHOD
const removeNote = async (removeNoteId) => {
    const res = await fetch(`http://localhost:5000/notes/${removeNoteId}`, {
        method: 'DELETE'
    })
    if (res.status === 200) {
        notes.value = notes.value.filter((note) => note.id !== removeNoteId)
        console.log('Delete successfully');
    } else
        console.log('error, cannot delete');
}

//POST METHOD
const createNewNote = async (newNote) => {
    const res = await fetch('http://localhost:5000/notes', {
        method: 'POST',
        headers: {
            'content-type': 'application/json'
        },
        body: JSON.stringify({ noteDetail: newNote })
    })
    if (res.status === 201) {
        const addedNote = await res.json()
        notes.value.push(addedNote)
        console.log('created successfully');
    } else
        console.log('error, cannot create');
}

// PUT METHOD
const editingNote = ref({})
const toEditMode = (editNote) => {
    console.log(editNote)
    editingNote.value = editNote
}
const updateNote = async (replaceNote) => {
    const res = await fetch(`http://localhost:5000/notes/${replaceNote.id}`, {
        method: 'PUT',
        headers: {
            'content-type': 'application/json'
        },
        body: JSON.stringify({
            noteDetail: replaceNote.noteDetail
        })
    })
    if (res.status === 200) {
        const editedNote = await res.json()
        notes.value = notes.value.map((note) =>
            note.id === editedNote.id
                ? { ...note, noteDetail: editedNote.noteDetail }
                : note
        )
        console.log('edited successfully')
    } else console.log('error, cannot be added')
    editingNote.value = {}
}
</script>

<template>
    <div>
        <CreateEditNote
            @createNote="createNewNote"
            :currentNote="editingNote"
            @updateNote="updateNote"
        />
        <NoteList :notes="notes" @deleteNote="removeNote" @editNote="toEditMode" />
    </div>
</template>
 
<style>
</style>