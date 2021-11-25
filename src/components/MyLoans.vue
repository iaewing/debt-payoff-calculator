<template>
  <div class="border-2">
    <p class="p-4 bg-blue-500 text-white text-2xl">My Loans</p>
    <p>{{ loan.amountOwing }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return { tacoCount2: 1233}
  },
  props: {
    loan: {
      type: Object
    },
  },
}
</script>

<style scoped>

</style>
