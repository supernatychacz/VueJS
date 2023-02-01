<script setup>
import { ref } from "vue";

const username = ref("username");

defineProps({
  msg: {
    type: String,
    required: true,
  },
  number: {
    type: Number,
  },
});

function printMessage() {
  alert("Button was clicked");
}
</script>

<template>
  <div class="greetings">
    <h1 class="green">{{ msg }}</h1>
    <h1 :class="number >= 20 ? 'green' : ''">{{ number }}</h1>
    <input v-model="username" placeholder="Enter your username" />
    {{ username }}
    <button @click="printMessage">Click Me</button>
  </div>
</template>

<style scoped>
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  top: -10px;
}

h3 {
  font-size: 1.2rem;
}

.greetings h1,
.greetings h3 {
  text-align: center;
}

@media (min-width: 1024px) {
  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}
</style>
