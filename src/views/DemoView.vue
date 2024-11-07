<script setup>
import ArsipDompetku from '@/components/Demo/ArsipDompetku.vue'
</script>

<template>
  <main>

    <ArsipDompetku class="large-spacing" />

  </main>
</template>
<style scoped>
.demo-container {
  background-color: #e0f7e0; /* Soft green background */
  padding: 20px;
  border-radius: 12px;
}

.component-section {
  background-color: #ffffff;
  border-radius: 8px;
  padding: 15px;
  margin-bottom: 20px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

.component-section h2 {
  color: #2e7d32; /* Darker green for headings */
  font-size: 1.5rem;
  margin-bottom: 10px;
}

button {
  background-color: #4caf50; /* Green button */
  color: #fff;
  padding: 8px 12px;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}

button:hover {
  background-color: #388e3c; /* Darker green on hover */
}

hr {
  border: none;
  height: 1px;
  background-color: #d0e7d0; /* Soft line color */
  margin: 20px 0;
}
</style>
