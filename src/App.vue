<template>
  <NavBar/>
  <div class="grid grid-cols-5 gap-x-4 p-8">
    <div class="border-2">
      <p class="p-4 bg-blue-500 text-white text-2xl">Payment Plan</p>
      <div class="p-4">
        Payment Plan Type
        <div class="flex items-center">
          <input type="radio" id="avalanche" class=""/>
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
          <p v-text="'$' + monthlyPayment" class="text-green-600 text-xl"></p>
          <input v-model="monthlyPayment" type="range" min="409" max="1000" class="appearance-none h-1 bg-blue-500 border-red-500 w-full"/>
        </div>
      </div>
    </div>
    <!--Start of column two-->
    <div class="col-span-4 grid grid-cols-4 gap-4">
      <Card class="bg-purple-600 text-white p-4">
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
</template>

<script>
import NavBar from './components/NavBar.vue'
import Card from './components/Card.vue'

export default {
  name: 'App',
  components: {
    NavBar,
    Card,
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
