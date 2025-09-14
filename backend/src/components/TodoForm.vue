<template>
  <form @submit.prevent="addTodo">
    <input v-model="title" placeholder="Title" required />
    <input v-model="description" placeholder="Description" />
    <select v-model="status">
      <option value="pending">Pending</option>
      <option value="in-progress">In Progress</option>
      <option value="completed">Completed</option>
    </select>
    <input type="date" v-model="due_date" />
    <button type="submit">Add Todo</button>
  </form>
</template>

<script setup>
import { ref } from "vue";
import api from "../api";

const title = ref("");
const description = ref("");
const status = ref("pending");
const due_date = ref("");

async function addTodo() {
  await api.post("/todos", {
    title: title.value,
    description: description.value,
    status: status.value,
    due_date: due_date.value
  });
  title.value = "";
  description.value = "";
  status.value = "pending";
  due_date.value = "";
  emit("todo-added");
}
</script>
