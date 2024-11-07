<template>
  <div class="container wallet p-4 bg-light rounded">
    <h1 class="text-center mb-4">Dompetku versi 3.0</h1>

    <!-- Form for adding entries -->
    <form @submit.prevent="addEntry" class="mb-4">
  <div class="row g-3">
    <!-- Input field for Description -->
    <div class="col-md-3">
      <input
        type="text"
        v-model="description"
        class="form-control"
        placeholder="Description"
        required
      />
    </div>

    <!-- Input field for Amount -->
    <div class="col-md-3">
      <input
        type="number"
        v-model="amount"
        class="form-control"
        placeholder="Amount"
        required
      />
    </div>

    <!-- Select for Type (Income or Expense) -->
    <div class="col-md-3">
      <select v-model="type" class="form-select" required>
        <option value="income">Income</option>
        <option value="expense">Expense</option>
      </select>
    </div>

    <!-- Select for Category -->
    <div class="col-md-3">
      <select v-model="category" class="form-select" required>
        <option v-for="cat in categories" :key="cat" :value="cat">{{ cat }}</option>
      </select>
    </div>
  </div>

  <!-- Row for the "Add Entry" button, aligned below input fields -->
  <div class="row mt-3">
    <div class="col-md-12">
      <button type="submit" class="btn btn-primary w-100">Add Entry</button>
    </div>
  </div>
</form>

    <!-- Summary Information -->
    <div class="card summary-card text-center mb-4">
      <div class="card-body">
        <h5 class="card-title">Summary</h5>
        <p>Total Entries: <strong>{{ totalEntries }}</strong></p>
        <p>Total Income: <strong class="text-success">{{ totalIncome }}</strong></p>
        <p>Total Expenses: <strong class="text-danger">{{ totalExpenses }}</strong></p>
        <p>Balance: <strong :class="{ 'text-success': balance >= 0, 'text-danger': balance < 0 }">{{ balance }}</strong></p>
      </div>
    </div>

    <!-- List of entries -->
    <ul class="list-group mb-4">
      <li class="list-group-item d-flex justify-content-between align-items-center" v-for="entry in entries" :key="entry.id">
        <div>
          <h6 class="mb-1">{{ entry.description }} - <small class="text-muted">{{ entry.category }}</small> ({{ entry.type }})</h6>
          <small>Amount: <span :class="entry.type === 'income' ? 'text-success' : 'text-danger'">{{ entry.amount }}</span></small>
        </div>
        <button class="btn btn-sm btn-danger" @click="deleteEntry(entry.id)">
          <i class="bi bi-trash"></i> Delete
        </button>
      </li>
    </ul>

    <!-- Delete All Button with Confirmation -->
    <button class="btn btn-danger w-100" @click="deleteAllEntries">Delete All Entries</button>
  </div>
</template>

<script setup>
import { ref, computed, watch } from 'vue'
import { v4 as uuidv4 } from 'uuid'
import Swal from 'sweetalert2'

// Initialize reactive variables
const entries = ref(JSON.parse(localStorage.getItem('entries')) || [])
const description = ref('')
const amount = ref(null)
const type = ref('income')
const category = ref('')
const categories = ['Food', 'Transport', 'Shoping', 'Entertainment', 'Other']

// Watch for changes in entries and save to localStorage
watch(entries, (newEntries) => {
  localStorage.setItem('entries', JSON.stringify(newEntries))
}, { deep: true })

// Add a new entry
const addEntry = () => {
  if (description.value && amount.value) {
    entries.value.push({
      id: uuidv4(),
      description: description.value,
      amount: parseFloat(amount.value),
      type: type.value,
      category: category.value,
    })
    description.value = ''
    amount.value = null
    category.value = ''
  }
}

// Delete a single entry
const deleteEntry = (id) => {
  entries.value = entries.value.filter(entry => entry.id !== id)
}

// Confirm before deleting all entries
const deleteAllEntries = () => {
  Swal.fire({
    title: 'Are you sure?',
    text: "This will delete all entries!",
    icon: 'warning',
    showCancelButton: true,
    confirmButtonText: 'Yes, delete all',
    cancelButtonText: 'Cancel',
  }).then((result) => {
    if (result.isConfirmed) {
      entries.value = []
      Swal.fire('Deleted!', 'All entries have been deleted.', 'success')
    }
  })
}

// Computed properties for summary
const totalEntries = computed(() => entries.value.length)
const totalIncome = computed(() => entries.value.filter(e => e.type === 'income').reduce((sum, entry) => sum + entry.amount, 0))
const totalExpenses = computed(() => entries.value.filter(e => e.type === 'expense').reduce((sum, entry) => sum + entry.amount, 0))
const balance = computed(() => totalIncome.value - totalExpenses.value)
</script>

<style scoped>
.wallet {
  max-width: 900px;
  margin: auto;
}
.wallet {
  max-width: 1200px; /* Adjust as needed */
  width: 100%;
  margin: auto;
  padding: 20px; /* Optional: add more padding */
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

.summary-card {
  background-color: #f8f9fa;
  border: 1px solid #dee2e6;
}

.text-success {
  color: #28a745 !important;
}

.text-danger {
  color: #dc3545 !important;
}
</style>
