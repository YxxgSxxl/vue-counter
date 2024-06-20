<script setup lang="ts">
import { ref } from 'vue'

defineProps({
  msg: String,
})

const count = ref<number>(0)

if (count.value = 0) {
  alert('here')
}

var reset = function() {
    count.value = 0
  }

function counter(operand: string): void
{
  if (operand == "minus") {
    count.value--
  }

  if (operand == "plus") {
    count.value++
  }

  if (count.value <= 0) {
    reset()
  }
}
</script>

<template>
  <h1>{{ msg }}</h1>

  <div class="card">
    <div class="counter">
      <button type="button" @click="counter('minus')">-</button>
      <div class="count">count is {{ count }}</div>
      <button type="button" @click="counter('plus')">+</button>
    </div>
    <button type="button" @click="reset()">Reset</button>
  </div>
</template>

<style scoped lang="scss">
.card {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: .5rem;

  button {
    user-select: none;
  }

  .counter {
    display: flex;
    gap: .5rem;
    
    .count {
      padding: 0.6rem 1rem 0.6rem 1rem;
      border-radius: 12px;
      background-color: inherit;
    }
  }
}
</style>
