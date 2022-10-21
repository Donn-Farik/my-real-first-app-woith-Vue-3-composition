<template>
  <div class="botonn">
    <button :class="className" @click="$emit('clickme')">
      {{ givemeName }}
    </button>
  </div>
</template>

<script setup>
const defineProps = defineProps({
  givemeName: {
    type: String,
  },
});
defineEmits(["clickme"]);
</script>

<style>
.botonn {
  display: flex;
  justify-content: center;
  margin-top: 30px;
  outline-color: none;
}
.botonn button {
  height: 30px;
  width: 100px;
  padding: 30px;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: bisque;
  font-family: "Times New Roman", Times, serif;
  border: none;
}
</style>
