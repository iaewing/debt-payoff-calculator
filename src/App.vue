<template>
  <NavBar/>
  <div class="grid grid-cols-5 grid-rows-5 gap-x-4 p-8">
    <div>
      <PaymentPlan :loans="loans" v-model="monthlyPayment" />
      <MyLoans @addLoan="registerLoan" :loan="loans[0]" />
    </div>
    <!--Start of column two-->
    <div class="col-span-4 row-span-1">
      <div class="grid grid-cols-4 gap-4">
        <Card class="bg-purple-600 text-white p-4 ">
          <template v-slot:default>
            ${{ totalPrincipalOwed }}
          </template>
          <template v-slot:header>
            <div>Principal Paid</div>
          </template>
          <template v-slot:subtext v-if="totalPrincipalOwed>=20000">
            Wow im broke
          </template>
          <template v-slot:subtext v-else>
            you can do it
          </template>
        </Card>
        <Card class="bg-green-400 text-white p-4">
          <template v-slot:default>
            {{ paidOffDate }} month(s)
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
            ${{ interestPaid }}
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
            {{ interestRate }}%
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
import MyLoans from "./components/MyLoans";

//TODO: Fix it. (Migrate to a array of loans vs single loan object)
const loans = [{
  name: 'OSAP',
  amountOwing: 15000,
  interestRate: 1.5,
  monthlyPayment: 250,
}, {
  name: 'Credit Card',
  amountOwing: 15000,
  interestRate: 1.5,
  monthlyPayment: 500,
}];


export default {
  name: 'App',
  components: {
    MyLoans,
    NavBar,
    Card,
    PaymentPlan
  },
  data() {
    return {
      monthlyPayment: 0,
      loans
    }
  },
  computed: {
    totalPrincipalOwed() {
      //iterate over each loan and tally the amountOwing
      return 2;
    },
    paidOffDate() {
      // return Math.floor((this.loan.amountOwing + this.interestPaid) / this.loan.monthlyPayment);
      return 50;
    },
    interestPaid() {
      // return this.loan.amountOwing * (this.interestRate / 100);
      return 100;
    },
    interestRate() {
      //This would be an average of each loan's interest rate
      return 1.5;

      // return this.loan.interestRate;
    },
  },
  methods: {
    registerLoan() {

    }
  }
}
</script>

<style>

</style>
