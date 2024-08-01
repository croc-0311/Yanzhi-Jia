<template>
  <div>
    <h1>Authors born after 1850</h1>
    <ul>
      <li v-for="author in modernAuthors" :key="author.id">
        {{ author.name }} ({{ author.birthYear }})
      </li>
    </ul>
    <button @click="showMessage = !showMessage">Toggle Message</button>
    <p v-if="showMessage">Hello, this is a toggled message!</p>
  </div>
</template>

<script>
import { ref, computed } from 'vue'
import authors from '../assets/json/authors.json'

export default {
  name: 'YjiaLibrary',
  setup() {
    const showMessage = ref(false)

    // Activity 2: Get authors born after 1850
    const modernAuthors = computed(() => {
      return authors.filter((author) => author.birthYear > 1850)
    })

    return {
      showMessage,
      modernAuthors
    }
  }
}
</script>

<style scoped>
h1 {
  color: blue;
}
</style>
