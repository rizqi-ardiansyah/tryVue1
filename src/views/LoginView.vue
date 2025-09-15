<script setup lang="ts">
import { ref } from "vue"
import { useRouter } from "vue-router"

const router = useRouter()
const email = ref("")
const password = ref("")
const error = ref("")

const login = () => {
  if (email.value === "admin@test.com" && password.value === "123456") {
    // Simulasi login sukses
    localStorage.setItem("auth", "true")
    router.push("/") // redirect ke dashboard
  } else {
    error.value = "Email atau password salah"
  }
}
</script>

<template>
  <div class="min-h-screen flex items-center justify-center bg-gray-100">
    <div class="bg-white p-8 rounded-lg shadow-lg w-96">
      <h1 class="text-2xl font-bold mb-6 text-center">Login</h1>

      <div v-if="error" class="mb-4 text-red-600 text-sm">{{ error }}</div>

      <div class="mb-4">
        <label class="block text-sm font-medium text-gray-700">Email</label>
        <input v-model="email" type="email" class="mt-1 block w-full p-2 border rounded-md" />
      </div>

      <div class="mb-6">
        <label class="block text-sm font-medium text-gray-700">Password</label>
        <input v-model="password" type="password" class="mt-1 block w-full p-2 border rounded-md" />
      </div>

      <button
        @click="login"
        class="w-full bg-blue-600 text-white py-2 rounded-md hover:bg-blue-700 transition"
      >
        Login
      </button>
    </div>
  </div>
</template>
