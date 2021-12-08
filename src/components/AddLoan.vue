<template>
  <div class="bg-white rounded shadow-lg overflow-hidden w-1/2">
    <header class="p-4 bg-blue-500 text-white text-2xl">Add Loan</header>
    <div class="grid gap-y-4 px-4 py-8">
      <ewing-input v-model="loanName" id="loan-name" placeholder="Loan Name" error=""/>
      <ewing-input v-model="principalRemaining" id="principal-remaining" placeholder="Principal Remaining" error=""/>
      <ewing-input v-model="interest" id="interest" placeholder="Interest (%)" error=""/>
      <ewing-input v-model="minimumPayment" id="min-payment" placeholder="Minimum Payment ($)" error=""/>
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
import EwingInput from "@/components/ewing-input";

export default {
  name: "Modal",
  components: {EwingInput},
  data() {
    return {
      loanName: '',
      principalRemaining: '',
      interest: '',
      minimumPayment: '',
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
