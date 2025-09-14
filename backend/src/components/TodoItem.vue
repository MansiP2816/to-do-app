<template>
  <div>
    <p>
      <strong>{{ todo.title }}</strong> - {{ todo.status }}
    </p>
    <button @click="markCompleted">Complete</button>
    <button @click="deleteTodo">Delete</button>
  </div>
</template>

<script setup>
import api from "../api";
const props = defineProps({ todo: Object });

async function markCompleted() {
  await api.put(`/todos/${props.todo.id}`, { status: "completed" });
  emit("updated");
}

async function deleteTodo() {
  await api.delete(`/todos/${props.todo.id}`);
  emit("updated");
}
</script>
