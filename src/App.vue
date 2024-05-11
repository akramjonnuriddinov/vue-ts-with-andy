<script setup lang="ts">
import { reactive } from "vue"
import Counter from "./components/Counter.vue"

interface AppInfo {
  name: string
  slogan: string
}

const appInfo: AppInfo = reactive({
  name: "13",
  slogan: "an app you can count",
})
</script>

<template>
  <div>
    <p>
      {{ appInfo.name }}
    </p>
    <p>
      {{ appInfo.slogan }}
    </p>
    <Counter :limit="10" />
  </div>
</template>
