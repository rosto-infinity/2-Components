<template>
  <label :for="id" class="flex items-center cursor-pointer">
    <input
      type="checkbox"
      :id="id"
      :checked="modelValue"
      @change="handleChange"
      class="hidden"
    />
    <span
      :class="{
        'bg-green-500': modelValue,
        'bg-gray-300': !modelValue,
      }"
      class="w-6 h-6 rounded-full inline-block transition-colors duration-300"
    ></span>
    <span class="ml-2">{{ label }}</span>
  </label>
</template>

<script setup>
import { defineProps, defineEmits } from 'vue';

const props = defineProps({
  modelValue: {
    type: Boolean,
    required: true,
  },
  label: {
    type: String,
    required: true,
  },
  id: {
    type: String,
    required: true,
  },
});

const emit = defineEmits(['update:modelValue']);

const handleChange = (event) => {
  emit('update:modelValue', event.target.checked);
};
</script>
