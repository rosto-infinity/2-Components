<template>
  <div>
    <input type="checkbox" v-model="checked" />
    <label> Lorem, ipsum dolor.</label>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const checked = ref(false);
</script>
