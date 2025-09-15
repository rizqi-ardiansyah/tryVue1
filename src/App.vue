<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import { ref } from 'vue'

const sidebarOpen = ref(false)

const toggleSidebar = () => {
  sidebarOpen.value = !sidebarOpen.value
}
</script>

<template>
  <div class="min-h-screen bg-gray-100 flex">
    <!-- Sidebar -->
    <div class="bg-gray-900 text-white w-64 min-h-screen p-4 space-y-6" :class="{ 'hidden': !sidebarOpen, 'block': sidebarOpen, 'md:block': true }">
      <div class="flex items-center space-x-2">
        <div class="w-8 h-8 bg-blue-600 rounded-lg flex items-center justify-center">
          <span class="text-white font-bold text-lg"></span>
        </div>
        <h1 class="text-xl font-bold">Tes Dashboard</h1>
      </div>

      <nav class="space-y-2">
        <RouterLink
          to="/"
          class="flex items-center space-x-2 p-2 rounded-lg hover:bg-gray-800 transition-colors"
          active-class="bg-blue-600"
        >
          <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 20 20">
            <path d="M10.707 2.293a1 1 0 00-1.414 0l-7 7a1 1 0 001.414 1.414L4 10.414V17a1 1 0 001 1h2a1 1 0 001-1v-2a1 1 0 011-1h2a1 1 0 011 1v2a1 1 0 001 1h2a1 1 0 001-1v-6.586l.293.293a1 1 0 001.414-1.414l-7-7z"></path>
          </svg>
          <span>Dashboard</span>
        </RouterLink>

        <RouterLink
          to="/about"
          class="flex items-center space-x-2 p-2 rounded-lg hover:bg-gray-800 transition-colors"
          active-class="bg-blue-600"
        >
          <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 20 20">
            <path fill-rule="evenodd" d="M18 10a8 8 0 11-16 0 8 8 0 0116 0zm-7-4a1 1 0 11-2 0 1 1 0 012 0zM9 9a1 1 0 000 2v3a1 1 0 001 1h1a1 1 0 100-2v-3a1 1 0 00-1-1H9z" clip-rule="evenodd"></path>
          </svg>
          <span>About</span>
        </RouterLink>
      </nav>
    </div>

    <!-- Main Content -->
    <div class="flex-1 flex flex-col">
      <!-- Header -->
      <header class="bg-white shadow-sm border-b border-gray-200 p-4 flex items-center justify-between">
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
