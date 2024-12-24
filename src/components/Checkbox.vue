<template>
  <label class="flex items-center space-x-2">
    <input type="checkbox" :checked="checked" @change="emitUpdate" class="form-checkbox h-5 w-5 text-blue-600">
    <span class="text-gray-900">Vérifie-moi</span>
  </label>
</template>

<script setup>
import { defineProps, defineEmits } from 'vue'

const props = defineProps({
  checked: Boolean
})

const emits = defineEmits(['updateChecked'])

const emitUpdate = (event) => {
  emits('updateChecked', event.target.checked)
}
</script>

<style scoped>
/* Styles additionnels si nécessaire */
</style>
