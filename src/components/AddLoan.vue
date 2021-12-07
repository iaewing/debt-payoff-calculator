<template>
  <div class="bg-white rounded shadow-lg overflow-hidden w-1/2">
    <header class="p-4 bg-blue-500 text-white text-2xl">Add Loan</header>
    <div class="grid gap-y-4 px-4 py-8">
<!--      extract these to their own component-->
      <input class="border-0 border-b border-gray-500 pl-0" type="text" placeholder="Loan Name">
      <input class="border-0 border-b border-gray-500 pl-0" type="text" placeholder="Principal Remaining ($)">
      <input class="border-0 border-b border-gray-500 pl-0" type="text" placeholder="Interest (%)">
      <input class="border-0 border-b border-gray-500 pl-0" type="text" placeholder="Monthly Minimum Payment ($)">
    </div>
    <footer class="flex justify-end p-4">
      <button class="font-semibold px-4 py-2" @click="$emit('closed')">
        CANCEL
      </button>
<!--      //TODO: Add some kind of check to ensure text fields are filled, toggle formIncomplete-->
      <button class="font-semibold px-6 py-2" :disabled="formIncomplete" :class="formIncomplete ? 'bg-gray-200' : 'bg-blue-500'">
        SAVE
      </button>
    </footer>
  </div>
</template>

<script>
export default {
  name: "Modal",
  data(){
    return {
      formIncomplete: true //make this computed, contributed to by the 4 inputs
    }
  }
}
</script>

<style scoped>

</style>
