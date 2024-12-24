<template>
  <label :for="id" class="flex items-center cursor-pointer">
    <input
      type="checkbox"
      :id="id"
      :checked="modelValue"
      @change="handleChange"
      class="hidden"
      :aria-checked="modelValue"
    />
    <span
      :class="{
        'bg-green-500 border-2 border-green-800': modelValue,
        'bg-red-200 border-2 border-green-600': !modelValue,
        'bg-gray-300 cursor-not-allowed': disabled,
      }"
      class="w-6 h-6 rounded-full inline-block transition-all transform  duration-300 scale-110 hover:scale-125"
    ></span>
    <span class="ml-2">{{ label }}</span>
  </label>
</template>
<script setup>

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
  disabled: { type: Boolean, default: false }, // Ajout de la prop disabled
});

const emits = defineEmits(['update:modelValue']);

const handleChange = (event) => {
  emits('update:modelValue', event.target.checked);
};
</script>
