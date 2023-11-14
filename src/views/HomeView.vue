<template>
  This is home
  {{ ha }}
</template>

<script setup lang="ts">
import { onMounted, ref } from 'vue';

const ha = ref("This is home")
onMounted(() => {
  for (const iterator of [1, 2, 3, 8, 7, 10]) {
    ha.value += `${iterator} hahahahhahaha`
  }
  for (let index = 0; index < 9999; index++) {
    ha.value += ` hahahahahaaaaaaaaaaaaaaaaaaaaaaaahahahahahahahahahhahaha`

  }
})
</script>