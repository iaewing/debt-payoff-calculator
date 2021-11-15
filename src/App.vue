<template>
  <NavBar />
  <div class="grid grid-cols-3 gap-x-5">
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
    <Card class="bg-yellow-600 text-white p-4">
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
    <Card class="bg-red-500 text-white p-4">
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
