<template>
  <div class="p-4">
    <Checkbox :checked="isChecked" @updateChecked="handleUpdateChecked" />
    <p>La case à cocher <span class="text-green-500">{{ isChecked ? 'checked' : 'unchecked' }}</span></p>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import Checkbox from './components/Checkbox.vue'

const isChecked = ref(false)

const handleUpdateChecked = (newValue) => {
  isChecked.value = newValue
}
</script>


