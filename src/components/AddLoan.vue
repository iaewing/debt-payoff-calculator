<template>
  <div class="bg-white rounded shadow-lg overflow-hidden w-1/2">
    <header class="p-4 bg-blue-500 text-white text-2xl">Add Loan</header>
    <div class="grid gap-y-4 px-4 py-8">
      <text-input v-model="loanName" id="loan-name" placeholder="Loan Name" error=""/>
      <text-input v-model="principalRemaining" id="principal-remaining" placeholder="Principal Remaining" error=""/>
      <text-input v-model="interest" id="interest" placeholder="Interest (%)" error=""/>
      <text-input v-model="minimumPayment" id="min-payment" placeholder="Minimum Payment ($)" error=""/>
    </div>
    <footer class="flex justify-end p-4">
      <button class="font-semibold px-4 py-2" @click="$emit('closed')">
        CANCEL
      </button>
      <button class="font-semibold px-6 py-2" :disabled="!formComplete" :class="formComplete ? 'bg-blue-500' : 'bg-gray-200'">
        SAVE
      </button>
    </footer>
  </div>
</template>

<script>
import TextInput from "@/components/TextInput";

export default {
  name: "Modal",
  components: {TextInput},
  data() {
    return {
      loanName: '',
      principalRemaining: '',
      interest: '',
      minimumPayment: '',
      errors: []
    }
  },
  computed: {
    formComplete() {
      return this.loanName && this.principalRemaining && this.interest && this.minimumPayment;
    }
  },
  //TODO: Add validation for inputs
}
</script>

<style scoped>

</style>
