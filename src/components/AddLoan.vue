<template>
  <div class="bg-white rounded shadow-lg overflow-hidden w-1/2">
    <header class="p-4 bg-blue-500 text-white text-2xl">Add Loan</header>
    <div class="grid gap-y-4 px-4 py-8">
      <text-input v-model="loan.loanName" id="loan-name" type="text" placeholder="Loan Name" error=""/>
      <text-input v-model.number="loan.principalRemaining" type="number" min="0" max="999999999" id="principal-remaining" placeholder="Principal Remaining ($)" error=""/>
      <text-input v-model.number="loan.interest" id="interest" type="number" min="0" max="100" placeholder="Interest (%)" error=""/>
      <text-input v-model.number="loan.minimumPayment" id="min-payment" type="number" min="1" placeholder="Minimum Payment ($)" error=""/>
    </div>
    <footer class="flex justify-end p-4">
      <button class="font-semibold px-4 py-2" @click="$emit('closed')">
        CANCEL
      </button>
      <button class="font-semibold px-6 py-2" @click="$emit('addLoan', this.loan)" :disabled="!formComplete" :class="formComplete ? 'bg-blue-500' : 'bg-gray-200'">
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
      loan: {
        loanName: '',
        principalRemaining: '',
        interest: '',
        minimumPayment: '',
      },
      errors: []
    }
  },
  computed: {
    formComplete() {
      return this.loan.loanName && this.loan.principalRemaining && this.loan.interest && this.loan.minimumPayment;
    }
  },
  //TODO: Close modal window on save
}
</script>

<style scoped>

</style>
