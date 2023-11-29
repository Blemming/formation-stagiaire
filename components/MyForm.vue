<template>
  <div>
  <h1>{{ answer }}</h1>
  <input v-model="expression" />
  <button @click="calculate">Calculate</button>
  </div>
</template>

<script lang="ts" setup>
const expression = ref('x^2-1')
const operation = ref('factor')
const answer = ref('')
async function calculate(){
    const response = await $fetch(`https://newton.now.sh/api/v2/${operation.value}/${expression.value}`)
    answer.value = response
}

</script>

<style>

</style>