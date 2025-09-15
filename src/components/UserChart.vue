<script setup lang="ts">
import { ref } from 'vue'
import {
  Chart as ChartJS,
  CategoryScale,
  LinearScale,
  BarElement,
  Title,
  Tooltip,
  Legend,
} from 'chart.js'
import { Bar } from 'vue-chartjs'

ChartJS.register(
  CategoryScale,
  LinearScale,
  BarElement,
  Title,
  Tooltip,
  Legend
)

const chartData = ref({
  labels: ['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun'],
  datasets: [
    {
      label: 'New Users',
      data: [1200, 1900, 1500, 2500, 2200, 3000],
      backgroundColor: 'rgba(147, 51, 234, 0.8)',
      borderColor: 'rgb(147, 51, 234)',
      borderWidth: 1
    }
  ]
})

const chartOptions = ref({
  responsive: true,
  maintainAspectRatio: false,
  plugins: {
    legend: {
      position: 'top' as const,
    },
  },
  scales: {
    y: {
      beginAtZero: true,
    }
  }
})
</script>

<template>
  <div class="h-64">
    <Bar
      :data="chartData"
      :options="chartOptions"
    />
  </div>
</template>