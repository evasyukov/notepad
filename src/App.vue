<template>
  <div id="app">
    <div class="title">
      <div class="title-text">Notepad</div>
      <button class="title-button_add" @click="addNote">+</button>
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

.title-text {
  color: aliceblue;
}

.title-button_add {
  height: 2vh;
  margin-left: 2vh;
}
</style>
