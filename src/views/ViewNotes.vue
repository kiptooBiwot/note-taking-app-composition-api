<script setup>
import { ref } from 'vue';
import Note from '../components/Notes/Note.vue';

/*
  Notes
*/
  const newNote = ref('')
  const newNoteRef = ref(null)
  const notes = ref([
    {
      id: 1,
      content: 'Lorem ipsum dolor sit, amet consectetur adipisicing elit. Atque eum, nam ab velit culpa quibusdam excepturi expedita itaque accusamus eius corporis dignissimos. Dolore, libero? Sequi quod labore cupiditate quisquam natus.'
    },
    {
      id: 2,
      content: 'This is a shorter note. It is way shorter than the Lorem ispsum dolor sit.'
    }
  ])

  /*
    methods
  */

 const addNewNote = () => {

  const currentDate = new Date().getTime(),
    id = currentDate.toString()

  // console.log(currentDate)

  const myNote = {
    id,
    content: newNote.value,
  }
  // Add to the front of the array
  notes.value.unshift(myNote)

// Clear the form
  newNote.value = ''

  // Set focus back to the form after saving a note
  newNoteRef.value.focus()
 }

 const deleteNote = (index) => {
    notes.value = notes.value.filter((note) => { return note.id != index })
    // console.log(index)
 }

</script>

<template>
  <div class="notes">
    <div class="card has-background-danger-dark mb-5 p-4">
      <div class="field">
        <div class="control">
          <textarea
            v-model="newNote"
            class="textarea"
            placeholder="Add a new note"
            ref="newNoteRef"
          />
        </div>
      </div>

      <div class="field is-grouped is-grouped-right">
        <div class="control">
          <button
            @click="addNewNote(newNote)"
            class="button is-link has-background-danger"
            :disabled="!newNote"
          >
            Add New Note
          </button>
        </div>
      </div>
    </div>
    <Note
      v-for="note in notes"
      :key="note.id"
      :note="note"
      @delete-clicked="deleteNote"
    />
  </div>
</template>

<style scoped>

</style>