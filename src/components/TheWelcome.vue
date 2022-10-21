<template>
  <div class="tanto">
    <h1 class="getred">{{ name }}</h1>
    <h1>{{ age }} years</h1>
  </div>
</template>

<script setup>
import { stringify } from "postcss";

defineProps({
  name: {
    type: String,
  },
  age: {
    type: Number,
  },
  type: {
    type: String,
  },
});
</script>

<style>
.getred {
  color: red;
}
.getgreen {
  color: green;
}
.tanto {
  display: flex;
  justify-content: center;
}
.tanto h1 {
  margin-left: 20px;
}
</style>
