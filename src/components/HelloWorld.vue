<script setup>
defineProps({
  msg: {
    type: String,
    required: true,
  },
})
</script>

<template>
  <div class="greetings">
    <h1 class="logo">ArsipDompetku</h1>
    <h2 class="green">{{ msg }}</h2>
    <h3>ANA SEMANGAT LAGI YA UNTUK HARI INI</h3>
    <h2>GO GO GO</h2>
    <h3>Gas Belajar Vue.js</h3>
  </div>
</template>

<style scoped>
/* Main logo style */
.logo {
  font-size: 3rem;
  font-weight: bold;
  color: #2e7d32; /* Dark green color */
  text-align: center;
  margin-bottom: 20px;
  letter-spacing: 2px;
}

/* Greeting text styles */
.green {
  font-weight: 600;
  font-size: 2rem;
  color: #4caf50; /* Bright green */
  margin: 10px 0;
}

h3 {
  font-size: 1.2rem;
  font-style: italic;
  color: #555;
  margin: 8px 0;
}

.greetings h1,
.greetings h2,
.greetings h3 {
  text-align: center;
}

.greetings {
  padding: 20px;
  background-color: #e0f7e0; /* Soft green background */
  border-radius: 10px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1); /* Soft shadow */
}

@media (min-width: 1024px) {
  .greetings h1,
  .greetings h2,
  .greetings h3 {
    text-align: left;
  }

  .greetings {
    padding: 40px;
  }
}
</style>
