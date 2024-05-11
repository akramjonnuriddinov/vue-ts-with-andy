<script setup lang="ts">
import { ref, onMounted } from "vue"
import fetchCount from "../fetchCount"

interface Props {
  limit: number
  alertMessageOnLimit: string
}

const props = withDefaults(defineProps<Props>(), {
  alertMessageOnLimit: "can not go any higher",
})

const count = ref<number | null>(null)

onMounted(() => {
  fetchCount((initialCount) => {
    count.value = initialCount
  })
})

function addCount(num: number) {
  if (count.value !== null) {
    if (count.value >= props.limit) {
      alert(props.alertMessageOnLimit)
    }
    count.value += num
  }
}
</script>

<template>
  <div>
    <p>
      {{ count }}
    </p>
    <button @click="addCount(2)">add</button>
  </div>
</template>
