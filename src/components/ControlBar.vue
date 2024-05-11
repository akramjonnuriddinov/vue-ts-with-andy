<script setup lang="ts">
const emit = defineEmits<{
  (event: "add-count", num: number): void
  (event: "reset-count"): void
}>()
</script>

<template>
  <button @click="emit('add-count', 2)">add</button>
  <button @click="emit('reset-count')">reset</button>
</template>
