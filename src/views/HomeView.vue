<script setup lang="ts">
import { ref } from 'vue'
import RevenueChart from '../components/RevenueChart.vue'
import UserChart from '../components/UserChart.vue'

// Sample dashboard data
const dashboardStats = ref([
  {
    title: 'Total Users',
    value: '12,345',
    change: '+12%',
    changeType: 'positive',
    icon: '👥'
  },
  {
    title: 'Revenue',
    value: '$45,678',
    change: '+8.2%',
    changeType: 'positive',
    icon: '💰'
  },
  {
    title: 'Orders',
    value: '1,234',
    change: '-2.4%',
    changeType: 'negative',
    icon: '📦'
  },
  {
    title: 'Growth Rate',
    value: '15.8%',
    change: '+3.1%',
    changeType: 'positive',
    icon: '📈'
  }
])

const recentActivity = ref([
  { id: 1, action: 'New user registration', time: '2 minutes ago' },
  { id: 2, action: 'Order completed', time: '5 minutes ago' },
  { id: 3, action: 'Payment received', time: '12 minutes ago' },
  { id: 4, action: 'Product viewed', time: '18 minutes ago' }
])
</script>

<template>
  <div class="space-y-6">
    <!-- Dashboard Header -->
    <div class="mb-8">
      <h1 class="text-3xl font-bold text-gray-900 mb-2">Dashboard Overview</h1>
      <p class="text-gray-600">Here's what's happening with your business today.</p>
    </div>

    <!-- Stats Cards -->
    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6 mb-8">
      <div
        v-for="stat in dashboardStats"
        :key="stat.title"
        class="bg-white rounded-lg shadow-sm border border-gray-200 p-6"
      >
        <div class="flex items-center justify-between mb-4">
          <div class="text-2xl">{{ stat.icon }}</div>
          <div
            :class="[
              'text-sm font-medium px-2 py-1 rounded-full',
              stat.changeType === 'positive'
                ? 'text-green-800 bg-green-100'
                : 'text-red-800 bg-red-100'
            ]"
          >
            {{ stat.change }}
          </div>
        </div>
        <div class="text-2xl font-bold text-gray-900 mb-1">{{ stat.value }}</div>
        <div class="text-sm text-gray-500">{{ stat.title }}</div>
      </div>
    </div>

    <!-- Charts and Activity Section -->
    <div class="grid grid-cols-1 lg:grid-cols-2 gap-6">
      <!-- Revenue Chart -->
      <div class="bg-white rounded-lg shadow-sm border border-gray-200 p-6">
        <h3 class="text-lg font-semibold text-gray-900 mb-4">Revenue & Profit Trends</h3>
        <RevenueChart />
      </div>

      <!-- Recent Activity -->
      <div class="bg-white rounded-lg shadow-sm border border-gray-200 p-6">
        <h3 class="text-lg font-semibold text-gray-900 mb-4">Recent Activity</h3>
        <div class="space-y-4">
          <div
            v-for="activity in recentActivity"
            :key="activity.id"
            class="flex items-center justify-between py-3 border-b border-gray-100 last:border-b-0"
          >
            <div class="flex items-center">
              <div class="w-2 h-2 bg-blue-500 rounded-full mr-3"></div>
              <span class="text-gray-900">{{ activity.action }}</span>
            </div>
            <span class="text-sm text-gray-500">{{ activity.time }}</span>
          </div>
        </div>
      </div>
    </div>

    <!-- User Growth Chart -->
    <div class="bg-white rounded-lg shadow-sm border border-gray-200 p-6 mb-6">
      <h3 class="text-lg font-semibold text-gray-900 mb-4">Monthly User Growth</h3>
      <UserChart />
    </div>

    <!-- Additional Info Cards -->
    <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
      <div class="bg-white rounded-lg shadow-sm border border-gray-200 p-6">
        <h3 class="text-lg font-semibold text-gray-900 mb-2">Performance</h3>
        <div class="text-3xl font-bold text-green-600 mb-1">98.5%</div>
        <p class="text-gray-500 text-sm">System uptime this month</p>
      </div>

      <div class="bg-white rounded-lg shadow-sm border border-gray-200 p-6">
        <h3 class="text-lg font-semibold text-gray-900 mb-2">Conversion</h3>
        <div class="text-3xl font-bold text-blue-600 mb-1">24.8%</div>
        <p class="text-gray-500 text-sm">Visitor to customer conversion</p>
      </div>

      <div class="bg-white rounded-lg shadow-sm border border-gray-200 p-6">
        <h3 class="text-lg font-semibold text-gray-900 mb-2">Satisfaction</h3>
        <div class="text-3xl font-bold text-yellow-600 mb-1">4.9/5</div>
        <p class="text-gray-500 text-sm">Average customer rating</p>
      </div>
    </div>
  </div>
</template>
