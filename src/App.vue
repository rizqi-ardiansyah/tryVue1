<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import { ref } from 'vue'

const sidebarOpen = ref(false)

const toggleSidebar = () => {
  sidebarOpen.value = !sidebarOpen.value
}
</script>

<template>
  <!-- Jika halaman adalah /login -->
  <div v-if="$route.path === '/login'" class="min-h-screen flex items-center justify-center bg-gray-100">
    <RouterView />
  </div>

  <!-- Jika halaman selain /login -->
  <div v-else class="min-h-screen bg-gray-100 flex">
    <!-- Sidebar -->
    <div
      class="bg-gray-900 text-white w-64 min-h-screen p-4 space-y-6"
      :class="{ 'hidden': !sidebarOpen, 'block': sidebarOpen, 'md:block': true }"
    >
      <div class="flex items-center space-x-2">
        <div class="w-8 h-8 bg-blue-600 rounded-lg flex items-center justify-center">
          <span class="text-white font-bold text-lg"></span>
        </div>
        <h1 class="text-xl font-bold">Tes Dashboard 1</h1>
      </div>

      <nav class="space-y-2">
        <RouterLink
          to="/"
          class="flex items-center space-x-2 p-2 rounded-lg hover:bg-gray-800 transition-colors"
          active-class="bg-blue-600"
        >
          <span>Dashboard</span>
        </RouterLink>

        <RouterLink
          to="/about"
          class="flex items-center space-x-2 p-2 rounded-lg hover:bg-gray-800 transition-colors"
          active-class="bg-blue-600"
        >
          <span>About</span>
        </RouterLink>
      </nav>
    </div>

    <!-- Main Content -->
    <div class="flex-1 flex flex-col">
      <!-- Header -->
      <header
        class="bg-white shadow-sm border-b border-gray-200 p-4 flex items-center justify-between"
      >
        <div class="flex items-center">
          <button
            @click="toggleSidebar"
            class="md:hidden p-2 rounded-md text-gray-400 hover:text-gray-500 hover:bg-gray-100"
          >
            <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"></path>
            </svg>
          </button>
          <h2 class="text-2xl font-semibold text-gray-800 ml-2">Welcome to Dashboard</h2>
        </div>
        <div class="flex items-center space-x-4">
          <div class="text-sm text-gray-500">{{ new Date().toLocaleDateString() }}</div>
        </div>
      </header>

      <!-- Main Content Area -->
      <main class="flex-1 p-6 overflow-auto">
        <RouterView />
      </main>
    </div>
  </div>
</template>
