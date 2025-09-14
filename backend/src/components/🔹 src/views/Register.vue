<template>
  <div>
    <h2>Register</h2>
    <form @submit.prevent="register">
      <input v-model="name" placeholder="Name" type="text" />
      <input v-model="email" placeholder="Email" type="email" />
      <input v-model="password" placeholder="Password" type="password" />
      <button type="submit">Register</button>
    </form>
    <p>Already have an account? <router-link to="/login">Login</router-link></p>
  </div>
</template>

<script setup>
import { ref } from "vue";
import { useRouter } from "vue-router";
import api from "../api";

const name = ref("");
const email = ref("");
const password = ref("");
const router = useRouter();

async function register() {
  try {
    await api.post("/register", {
      name: name.value,
      email: email.value,
      password: password.value
    });
    router.push("/login");
  } catch (error) {
    alert("Registration failed");
  }
}
</script>
