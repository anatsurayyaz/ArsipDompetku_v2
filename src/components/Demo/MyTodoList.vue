<script setup>
import { ref } from 'vue'
import MyTodoItem from './MyTodoItem.vue'

const groceryList = ref([
  { id: 0, text: 'Bakso' },
  { id: 1, text: 'Mie Goreng' },
  { id: 2, text: 'Apapun yang bisa dimakan manusia' },
])

const counterId = ref(3)
const todoText = ref('')
const submit = () => {
  groceryList.value.push({ id: counterId, text: todoText.value })
  counterId.value++
}
</script>

<template>
  <div>
    <input v-model="todoText" />
    <button @click="submit">Add</button>
    <ol>
      <!--
      We are providing each todo-item with the todo object
      it's representing, so that its content can be dynamic.
      We also need to provide each component with a "key",
      which is explained in the guide section on v-for.
    -->
      <MyTodoItem v-for="item in groceryList" :todo="item" :key="item.id"></MyTodoItem>
    </ol>
  </div>
</template>
