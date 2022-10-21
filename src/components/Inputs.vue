<template>
  <div class="container">
    <div class="inputs">
      <input
        type="text"
        :value="modelValue"
        @input="$emit('update:modelValue', $event.target.value)"
      />
    </div>
  </div>
</template>

<script setup>
const define = defineProps({
  modelValue: {
    type: String,
    default: "",
    required: true,
  },
});
</script>

<style scoped></style>
