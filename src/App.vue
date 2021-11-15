<template>
  <NavBar/>
  <div class="grid grid-cols-2">
    <div>
    </div>
    <div class="grid grid-cols-4 gap-x-5 max-w-3xl">
      <Card class="bg-purple-500 text-white p-4">
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
  }
}
</script>

<style>

</style>
