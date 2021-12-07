<template>
  <div class="border-2">
    <header class="relative p-4 bg-blue-500 text-white text-2xl">
      <span>My Loans</span>
      <button @click="openModal"
              class="bg-green-500 rounded-full overflow-hidden text-white p-3 absolute bottom-0 right-0 -mb-6 mr-3">
        <svg viewBox="0 0 24 24" class="w-6 h-6 fill-current">
          <path d="M19 13h-6v6h-2v-6H5v-2h6V5h2v6h6v2z"></path>
        </svg>
      </button>
    </header>
    <p>{{ loan.amountOwing }}</p>
    <teleport to="body">
      <div v-if="isModalOpen" class="bg-gray-700 bg-opacity-75 fixed top-0 left-0 w-screen h-screen z-10 flex items-center justify-center">
        <AddLoan @closed="closeModal" />
      </div>
    </teleport>
  </div>
</template>

<script>
import { ref } from 'vue'
import AddLoan from '@/components/AddLoan'

export default {
  components: {
    AddLoan
  },
  props: {
    loan: {
      type: Object
    },
  },
  setup() {
    let isModalOpen = ref(false)

    function openModal() {
      isModalOpen.value = true
    }

    function closeModal() {
      isModalOpen.value = false
    }

    return { isModalOpen, openModal, closeModal }
  }
}
</script>
