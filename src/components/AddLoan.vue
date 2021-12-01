<template>
  <div class="bg-white rounded shadow-lg overflow-hidden">
    <header class="p-4 bg-blue-500 text-white text-2xl">Add Loan</header>
    I'm a teleported modal!
    (My parent is "body")
    <footer>
      <button @click="$emit('closed')">
        Cancel
      </button>
      <button>
        Save
      </button>
    </footer>
  </div>
</template>

<script>
export default {
  name: "Modal"
}
</script>

<style scoped>

</style>
