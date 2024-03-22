<template>
  <div class="list">
    <div v-for="(note, index) in notes" :key="note.id">
      <textarea
        v-model="note.text"
        @input="saveNotes"
        placeholder="Введите текст..."
      >
      </textarea>
      <button @click="removeNote(index)">Удалить</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      notes: JSON.parse(localStorage.getItem("notes")) || [],
    }
  },
  methods: {
    saveNotes() {
      localStorage.setItem("notes", JSON.stringify(this.notes))
    },
    addNote() {
      const newNote = {
        id: Date.now(),
        text: "",
      }
      this.notes.push(newNote)
      this.saveNotes()
    },
    removeNote(index) {
      this.notes.splice(index, 1)
      this.saveNotes()
    },
  },
}
</script>

<style scoped>
textarea {
  min-width: 15vw;
  height: 25vh;
  padding: 10px;
  margin: 10px;
  box-sizing: border-box;
}
.list {
  display: flex;
}
</style>
