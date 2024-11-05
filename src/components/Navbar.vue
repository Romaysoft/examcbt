<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <nav class="fixed top-0 left-0 right-0 bg-white shadow-lg z-50 transition-all duration-300" :class="{ 'backdrop-blur-lg bg-white/90': isScrolled }">
    <div class="max-w-7xl mx-auto px-4">
      <div class="flex justify-between items-center h-16">
        <!-- Logo -->
        <div class="flex-shrink-0">
          <img class="h-8 w-auto" src="../assets/logo.svg" alt="Logo">
        </div>

        <!-- Desktop Menu -->
        <div class="hidden md:flex items-center space-x-8">
          <a href="#" class="text-gray-700 hover:text-blue-600">Dashboard</a>
          <a href="#" class="text-gray-700 hover:text-blue-600">Practice Tests</a>
          <a href="#" class="text-gray-700 hover:text-blue-600">Study Materials</a>
          <a href="#" class="text-gray-700 hover:text-blue-600">Results</a>
          <a href="#" class="text-gray-700 hover:text-blue-600">Support</a>
        </div>

        <!-- Buttons -->
        <div class="hidden md:flex items-center space-x-4">
          <button class="px-4 py-2 text-blue-700">
            Student Login
          </button>
          <button class="px-4 py-2 bg-blue-600 text-white rounded-md hover:bg-blue-700">
            Start Exam
          </button>
        </div>

        <!-- Mobile menu button -->
        <div class="md:hidden">
          <button
            @click="isOpen = !isOpen"
            class="text-gray-700 hover:text-blue-600"
          >
            <svg
              class="h-6 w-6"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
            >
              <path
                v-if="!isOpen"
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M4 6h16M4 12h16M4 18h16"
              />
              <path
                v-else
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M6 18L18 6M6 6l12 12"
              />
            </svg>
          </button>
        </div>
      </div>
    </div>

    <!-- Mobile Menu -->
    <div
      v-show="isOpen"
      class="md:hidden"
    >
      <div class="px-2 pt-2 pb-3 space-y-1">
        <a
          href="#"
          class="block px-3 py-2 text-gray-700 hover:text-blue-600"
        >Dashboard</a>
        <a
          href="#"
          class="block px-3 py-2 text-gray-700 hover:text-blue-600"
        >Practice Tests</a>
        <a
          href="#"
          class="block px-3 py-2 text-gray-700 hover:text-blue-600"
        >Study Materials</a>
        <a
          href="#"
          class="block px-3 py-2 text-gray-700 hover:text-blue-600"
        >Results</a>
        <a
          href="#"
          class="block px-3 py-2 text-gray-700 hover:text-blue-600"
        >Support</a>
      </div>
      <div class="px-4 py-3 space-y-2">
        <button class="w-full px-4 py-2 text-gray-700 hover:text-blue-600">
          Student Login
        </button>
        <button class="w-full px-4 py-2 bg-blue-600 text-white rounded-md hover:bg-blue-700">
          Start Exam
        </button>
      </div>
    </div>
  </nav>
  <!-- Add a spacer div to prevent content from jumping -->
  <div class="h-16"></div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const isOpen = ref(false)
const isScrolled = ref(false)

// Handle scroll event
const handleScroll = () => {
  isScrolled.value = window.scrollY > 0
}

// Add and remove scroll event listener
onMounted(() => {
  window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>
