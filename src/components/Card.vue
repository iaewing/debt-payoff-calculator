<template>
  <div class="flex flex-col max-w-2xl">
    <div class="text-lg">
      <slot name="header" />
    </div>
    <div class="text-3xl font-bold">
      <slot></slot>
    </div>
    <div>
      <slot name="subtext"></slot>
    </div>
  </div>
</template>

<script>
export default {
  name: "Card"
}
</script>
