<template>
  <div>
    <h3>My Todos</h3>
    <div v-for="todo in todos" :key="todo.id">
      <todo-item :todo="todo" @updated="emit('todo-updated')" />
    </div>
  </div>
</template>

<script setup>
import TodoItem from "./TodoItem.vue";
defineProps({ todos: Array });
</script>
