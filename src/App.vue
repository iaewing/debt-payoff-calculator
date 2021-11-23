<template>
  <NavBar/>
  <div class="grid grid-cols-5 grid-rows-5 gap-x-4 p-8">
    <PaymentPlan />

    <!--Start of column two-->
    <div class="col-span-4 row-span-1">
      <div class="grid grid-cols-4 gap-4">
        <Card class="bg-purple-600 text-white p-4 ">
          <template v-slot:default>
            $45,000.00
          </template>
          <template v-slot:header>
            <div>Principal Paid</div>
          </template>
          <template v-slot:subtext>
            Wow im broke
          </template>
        </Card>
        <Card class="bg-green-400 text-white p-4">
          <template v-slot:default>
            600 Years
          </template>
          <template v-slot:header>
            <div>Paid Off</div>
          </template>
          <template v-slot:subtext>
            That's a long time...
          </template>
        </Card>
        <Card class="bg-red-500 text-white p-4">
          <template v-slot:default>
            1.5%
          </template>
          <template v-slot:header>
            <div>Interest Paid</div>
          </template>
          <template v-slot:subtext>
            RIP
          </template>
        </Card>
        <Card class="bg-yellow-400 text-white p-4">
          <template v-slot:default>
            1.5%
          </template>
          <template v-slot:header>
            <div>Average Interest Rate</div>
          </template>
          <template v-slot:subtext>
            Your average interest rate across all loans
          </template>
        </Card>
      </div>

    </div>
  </div>
</template>

<script>
import NavBar from './components/NavBar.vue'
import Card from './components/Card.vue'
import PaymentPlan from './components/PaymentPlan.vue'

export default {
  name: 'App',
  components: {
    NavBar,
    Card,
    PaymentPlan
  },
  data () {
    return {
      monthlyPayment: 409,
    }
  }
}
</script>

<style>

</style>
