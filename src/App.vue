<template>
  <div id="app">
    <div class="title">
      <h1>Notepad</h1>
      <button @click="addNote">+</button>
    </div>
    <Notepad ref="notepad" />
  </div>
</template>

<script>
import Notepad from "./components/Notepad.vue"

export default {
  components: {
    Notepad,
  },
  methods: {
    addNote() {
      this.$refs.notepad.addNote()
    },
  },
}
</script>

<style>
.title {
  padding: 15px;
  display: flex;
  align-items: center;
}
.title button {
  height: 2vh;
  margin-left: 2vh;
}
.title h1 {
  color: aliceblue;
}
</style>
