<template>
  <div class="about">
    <div class="content">
      <h1>Website ini dibuat untuk belajar Vue.js.</h1>
      <h1>Klik Button untuk mencoba</h1>
      <router-link to="/demo">
        <button>Go to Demo</button>
      </router-link>
    </div>
  </div>
</template>

<style scoped>
.about {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
  text-align: center;
}

.content h1 {
  margin-bottom: 1rem;
}

button {
  padding: 0.5rem 1rem;
  font-size: 1rem;
  color: white;
  background-color: #4CAF50; /* Green */
  border: none;
  border-radius: 4px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

button:hover {
  background-color: #45a049;
}
</style>
