<template>
  <label :for="$attrs.id">{{ $attrs.placeholder }}</label>
  <input
      v-bind="$attrs"
      @input="$emit('update:modelValue', $event.target.value)"
      class="border-0 border-b border-gray-500 pl-0"
  />
  <span class="text-red-600">{{ error }}</span>
</template>

<script>
export default {
  name: "text-input",
  inheritAttrs: false,
  props: {
    modelValue: {
      type: String,
      default: "",
    },
    error: {
      type: String,
      default: ""
    }
  },
  emits: ['update:modelValue']
}
</script>

<style scoped>

</style>