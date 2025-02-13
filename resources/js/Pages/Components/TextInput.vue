<script setup>
const model = defineModel({
  type: null,
  required: true
})

defineProps({
  name: {
    type: String,
    required: true
  },
  type: {
    type: String,
    default: 'text'
  },
  message: String,
  id: String
})
</script>

<template>
  <div class="mb-6">
    <label :for="id">{{ name }}</label>
    <input :type="type" :id="id" v-model="model" :class="{ '!ring-red-500': message }" />
    <small class="error" v-if="message">{{ message }}</small>
  </div>
</template>