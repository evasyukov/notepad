<template>
  <div class="notes-list">
    <div class="notes" v-for="(note, index) in notes" :key="note.id">
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
.notes-list {
  display: flex;
  flex-wrap: wrap;
  width: 80%;
}
.notes {
  display: flex;
  flex-direction: column;
  align-items: center;

  margin: 10px;
  width: 20%;

  border: 2px solid rgb(106, 104, 104);
  border-radius: 5px;
  
  box-shadow: 1px 1px 10px rgb(92, 92, 92);

  & textarea {
    width: 100%;
    height: 250px;
    padding: 10px;
    box-sizing: border-box;
    resize: none;
  }

  & button {
    height: 50px;
    width: 100%;

    font-size: 100%;
  }
}
</style>
