<script setup>
const props = defineProps({
  todo: Object,
  postText: {
    type: [String, null],
  },
})
</script>

<template>
  <li>{{ props.todo.id }} {{ props.todo.text }} {{ props.postText ?? '' }}</li>
</template>
