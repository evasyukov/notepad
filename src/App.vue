<template>
  <div class="title">
    <div>Notepad</div>
    <button class="title-button_add" @click="addNote">+</button>
  </div>
  <Notepad ref="notepad" />
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
body {
  background-color: #242424;
}

#app {
  display: flex;
  flex-direction: column;
  align-items: center;

  font-family: Avenir, Helvetica, Arial, sans-serif;
}

.title {
  display: flex;
  align-items: center;

  gap: 10px;

  padding: 15px;

  color: aliceblue;
}

.title-button_add {
  height: 30px;
  width: 30px;

  color: #fff;
  background-color: #6b6b6b;

  border: none;
  border-radius: 5px;

  font-size: 22px;
}
</style>
