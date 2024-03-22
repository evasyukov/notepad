<template>
  <div>
    <textarea
      v-model="note"
      @input="saveNote"
      placeholder="Введите текст..."
    ></textarea>
  </div>
</template>

<script>

</script>

<style scoped>
textarea {
  min-width: 30vw;
  height: 50vh;
  padding: 10px;
  margin: 10px;
  box-sizing: border-box;
}
</style>
