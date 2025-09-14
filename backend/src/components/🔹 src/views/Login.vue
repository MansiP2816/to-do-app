<template>
  <div>
    <h2>Login</h2>
    <form @submit.prevent="login">
      <input v-model="email" placeholder="Email" type="email" />
      <input v-model="password" placeholder="Password" type="password" />
      <button type="submit">Login</button>
    </form>
    <p>Don’t have an account? <router-link to="/register">Register</router-link></p>
  </div>
</template>

<script setup>
import { ref } from "vue";
import { useRouter } from "vue-router";
import api from "../api";

const email = ref("");
const password = ref("");
const router = useRouter();

async function login() {
  try {
    await api.post("/login", { email: email.value, password: password.value });
    localStorage.setItem("user", email.value);
    router.push("/dashboard");
  } catch (error) {
    alert("Login failed");
  }
}
</script>
