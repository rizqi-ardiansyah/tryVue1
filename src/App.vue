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
        <aside
          class="w-64 bg-gray-900 text-white flex flex-col p-4 space-y-6"
          :class="{ 'hidden': !sidebarOpen, 'block': sidebarOpen, 'md:block': true }"
        >
          <div class="flex items-center space-x-2">
            <div class="w-8 h-8 bg-blue-600 rounded-lg flex items-center justify-center">
              <span class="font-bold text-lg"></span>
            </div>
            <h1 class="text-xl font-bold">My Dashboard</h1>
          </div>

          <nav class="space-y-2">
            <RouterLink
              to="/"
              class="flex items-center space-x-2 p-2 rounded-lg hover:bg-gray-800 transition-colors"
              active-class="bg-blue-600"
            >
              <span>🏠</span>
              <span>Home</span>
            </RouterLink>
            <RouterLink
              to="/reports"
              class="flex items-center space-x-2 p-2 rounded-lg hover:bg-gray-800 transition-colors"
              active-class="bg-blue-600"
            >
              <span>📊</span>
              <span>Reports</span>
            </RouterLink>
            <RouterLink
              to="/settings"
              class="flex items-center space-x-2 p-2 rounded-lg hover:bg-gray-800 transition-colors"
              active-class="bg-blue-600"
            >
              <span>⚙️</span>
              <span>Settings</span>
            </RouterLink>
          </nav>
        </aside>

        <!-- Main Content -->
        <div class="flex-1 flex flex-col">
          <!-- Header -->
          <header class="bg-white shadow-sm border-b border-gray-200 p-4 flex items-center justify-between">
            <div class="flex items-center">
              <button
                @click="toggleSidebar"
                class="md:hidden p-2 rounded-md text-gray-500 hover:text-gray-700"
              >
                ☰
              </button>
              <h2 class="text-2xl font-semibold text-gray-800 ml-2">Dashboard</h2>
            </div>
            <div class="flex items-center space-x-4">
              <span class="text-sm text-gray-600">Hi, Rizqi 👋</span>
             
            </div>
          </header>

          <!-- Content -->
          <main class="p-6 space-y-6 overflow-auto">
            <!-- Statistik Cards -->
            <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
              <div class="bg-white p-6 rounded-2xl shadow-md">
                <h3 class="text-gray-500 text-sm">Users</h3>
                <p class="text-2xl font-bold text-blue-600">1,240</p>
              </div>
              <div class="bg-white p-6 rounded-2xl shadow-md">
                <h3 class="text-gray-500 text-sm">Sales</h3>
                <p class="text-2xl font-bold text-green-600">$8,430</p>
              </div>
              <div class="bg-white p-6 rounded-2xl shadow-md">
                <h3 class="text-gray-500 text-sm">Tickets</h3>
                <p class="text-2xl font-bold text-red-600">32</p>
              </div>
            </div>

            <!-- Tabel Data -->
            <div class="bg-white p-6 rounded-2xl shadow-md">
              <h3 class="text-lg font-semibold mb-4">Recent Activity</h3>
              <table class="w-full text-left border-collapse">
                <thead>
                  <tr class="bg-gray-100">
                    <th class="p-2">User</th>
                    <th class="p-2">Activity</th>
                    <th class="p-2">Date</th>
                  </tr>
                </thead>
                <tbody>
                  <tr class="border-t">
                    <td class="p-2">Rizqi</td>
                    <td class="p-2">Logged in</td>
                    <td class="p-2">2025-09-15</td>
                  </tr>
                  <tr class="border-t">
                    <td class="p-2">Dewi</td>
                    <td class="p-2">Purchased item</td>
                    <td class="p-2">2025-09-14</td>
                  </tr>
                  <tr class="border-t">
                    <td class="p-2">Budi</td>
                    <td class="p-2">Updated profile</td>
                    <td class="p-2">2025-09-13</td>
                  </tr>
                </tbody>
              </table>
            </div>
          </main>
        </div>

  </div>
</template>
