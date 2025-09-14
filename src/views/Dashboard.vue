<template>
  <div>
    <h2>Dashboard</h2>
    <button @click="logout">Logout</button>
    <todo-form @todo-added="fetchTodos" />
    <todo-list :todos="todos" @todo-updated="fetchTodos" />
  </div>
</template>

<script setup>
import { ref, onMounted } from "vue";
import api from "../api";
import TodoForm from "../components/TodoForm.vue";
import TodoList from "../components/TodoList.vue";

const todos = ref([]);

async function fetchTodos() {
  const res = await api.get("/todos");
  todos.value = res.data;
}

async function logout() {
  await api.post("/logout");
  localStorage.removeItem("user");
  window.location.href = "/login";
}

onMounted(fetchTodos);
</script>
