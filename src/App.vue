<script setup>
import { ref, computed } from "vue";
import HelloWorld from "./components/HelloWorld.vue";
import TheWelcome from "./components/TheWelcome.vue";
import Inputs from "./components/Inputs.vue";
import Botones from "./components/Botones.vue";
const showme = ref("");
const showmetwo = ref("");
const showResult = ref([]);
const handleConfirmation = (el) => {
  el.done = !el.done;
};
const handleDelete = (index) => {
  showResult.value.splice(index, 1);
};
const handlClick = () => {
  console.log(showme.value * showmetwo.value);
  const result = showme.value * showmetwo.value;
  showResult.value.push({
    id: Math.floor(Math.random() * 100),
    content: result,
    done: false,
  });
  showme.value = "";
  showmetwo.value = "";
};
</script>

<template>
  <header>
    <div class="wrapper">
      <HelloWorld msg="Today is for props" />
    </div>
  </header>

  <main>
    <TheWelcome name="Farik" age="36" givemeName="Click " />
    <h2>Calculate</h2>
    <div class="input-dev">
      <Inputs v-model="showme" />
      *
      <Inputs v-model="showmetwo" />
    </div>
    <Botones @clickme="handlClick" givemeName="Calculate" />

    <template v-for="(el, index) in showResult" :key="el.id">
      <div class="container" :class="{ getColor: el.done }">
        <div class="myNumbers" :class="{ done: el.done }">{{ el.content }}</div>
        <Botones givemeName="X" @clickme="handleDelete(index)" />
        <Botones givemeName="Done" @clickme="handleConfirmation(el)" />
      </div>
    </template>
  </main>
</template>

<style scoped>
.input-dev {
  display: flex;
  justify-content: center;
}
main h2 {
  display: flex;
  justify-content: center;
}
.myNumbers {
  display: flex;
  justify-content: center;
  margin-top: 30px;
  font-size: 50px;
}
.done {
  text-decoration-line: line-through;
}
.getColor {
  color: green;
}
</style>
