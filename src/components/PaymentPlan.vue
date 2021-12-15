<template>
  <div class="border-2">
    <p class="p-4 bg-blue-500 text-white text-2xl">Payment Plan</p>
    <div class="p-4">
      Payment Plan Type
      <div class="flex items-center">
        <input type="radio" id="avalanche" class="" checked="paymentType=='avalanche'" v-model="paymentType" value="avalanche"/>
        <label for="avalanche" class="p-4">
          Highest Interest Rate <br/>
          (Avalanche)
        </label>
      </div>

      <div class="flex items-center">
        <input type="radio" id="snowball"/>
        <label for="snowball" class="p-4">
          Lowest Principal <br/>
          (Snowball)
        </label>
      </div>
      <div class="pt-4 mt-4 border-t border-black">
        <h3>Monthly Payment</h3>
        <p v-text="'$' + modelValue" class="text-green-600 text-xl"></p>
        <input value="monthlyPayment" @input="$emit('update:modelValue', Number($event.target.value))" type="range" :min=minimumMonthlyPayment max="10000" class="appearance-none h-1 bg-blue-500 border-red-500 w-full"/>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "PaymentPlan.vue",
  data() {
    return {
      paymentType: '',

    }
  },
  props: {
    loans: {
      type: Array,
      default: () => [],
    },
    modelValue: {
      type: Number,
    }
  },
  computed: {
    minimumMonthlyPayment() {
      return this.loans.reduce((total, loan) => {
        return total += loan.monthlyPayment;
      }, 0)
    }
  },
  mounted() {
    this.$emit('update:modelValue', this.minimumMonthlyPayment);
  }
}
</script>

<style scoped>

</style>
