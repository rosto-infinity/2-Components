<template>
  <div>
    <h2>{{ message }}</h2>
    <button @click="notifyParent">Cliquez-moi</button>
  </div>
</template>

<script setup>
import { defineProps, defineEmits } from 'vue'

// Définition des props
const props = defineProps({
  message: {
    type: String,
    required: true
  }
})

// Définition des événements
const emit = defineEmits(['notify'])

// Méthode pour notifier le parent
const notifyParent = () => {
  emit('notify', 'Le bouton a été cliqué!')
}
</script>


