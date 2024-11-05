<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <section class="py-20 bg-gray-50">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <!-- Header -->
      <div class="text-center max-w-3xl mx-auto mb-16">
        <h2 class="text-3xl font-bold text-gray-900 sm:text-4xl mb-4">
          Trusted by over 270,000 teachers across the world
        </h2>
        <p class="text-lg text-gray-600">
          Our platform has helped millions of students achieve their academic goals through innovative computer-based testing
        </p>
      </div>

      <!-- Stats Grid -->
      <div class="grid grid-cols-2 lg:grid-cols-4 gap-8">
        <!-- Students Tested -->
        <div class="text-center p-6 bg-blue-50 rounded-2xl">
          <div class="inline-flex items-center justify-center w-16 h-16 bg-blue-100 rounded-full mb-4">
            <svg class="w-8 h-8 text-blue-600" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 20h5v-2a3 3 0 00-5.356-1.857M17 20H7m10 0v-2c0-.656-.126-1.283-.356-1.857M7 20H2v-2a3 3 0 015.356-1.857M7 20v-2c0-.656.126-1.283.356-1.857m0 0a5.002 5.002 0 019.288 0M15 7a3 3 0 11-6 0 3 3 0 016 0zm6 3a2 2 0 11-4 0 2 2 0 014 0zM7 10a2 2 0 11-4 0 2 2 0 014 0z" />
            </svg>
          </div>
          <div class="text-4xl font-bold text-gray-900 mb-2">
            <span ref="studentsCounter">2.4M+</span>
          </div>
          <p class="text-gray-600 font-medium">Students Tested</p>
        </div>

        <!-- Tests Completed -->
        <div class="text-center p-6 bg-green-50 rounded-2xl">
          <div class="inline-flex items-center justify-center w-16 h-16 bg-green-100 rounded-full mb-4">
            <svg class="w-8 h-8 text-green-600" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5H7a2 2 0 00-2 2v12a2 2 0 002 2h10a2 2 0 002-2V7a2 2 0 00-2-2h-2M9 5a2 2 0 002 2h2a2 2 0 002-2M9 5a2 2 0 012-2h2a2 2 0 012 2m-6 9l2 2 4-4" />
            </svg>
          </div>
          <div class="text-4xl font-bold text-gray-900 mb-2">
            <span ref="testsCounter">5.7M+</span>
          </div>
          <p class="text-gray-600 font-medium">Tests Completed</p>
        </div>

        <!-- Success Rate -->
        <div class="text-center p-6 bg-purple-50 rounded-2xl">
          <div class="inline-flex items-center justify-center w-16 h-16 bg-purple-100 rounded-full mb-4">
            <svg class="w-8 h-8 text-purple-600" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 7h8m0 0v8m0-8l-8 8-4-4-6 6" />
            </svg>
          </div>
          <div class="text-4xl font-bold text-gray-900 mb-2">
            <span ref="successCounter">98%</span>
          </div>
          <p class="text-gray-600 font-medium">Success Rate</p>
        </div>

        <!-- Countries -->
        <div class="text-center p-6 bg-orange-50 rounded-2xl">
          <div class="inline-flex items-center justify-center w-16 h-16 bg-orange-100 rounded-full mb-4">
            <svg class="w-8 h-8 text-orange-600" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3.055 11H5a2 2 0 012 2v1a2 2 0 002 2 2 2 0 012 2v2.945M8 3.935V5.5A2.5 2.5 0 0010.5 8h.5a2 2 0 012 2 2 2 0 104 0 2 2 0 012-2h1.064M15 20.488V18a2 2 0 012-2h3.064M21 12a9 9 0 11-18 0 9 9 0 0118 0z" />
            </svg>
          </div>
          <div class="text-4xl font-bold text-gray-900 mb-2">
            <span ref="countriesCounter">50+</span>
          </div>
          <p class="text-gray-600 font-medium">Countries</p>
        </div>
      </div>

      <!-- Additional Info -->
      <div class="mt-16 text-center">
        <p class="text-gray-500 max-w-2xl mx-auto">
          Join the growing community of educators and institutions who trust our platform for their examination needs.
        </p>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted } from 'vue'

// Counter animation function
const animateCounter = (element, target, duration = 2000, prefix = '', suffix = '') => {
  let start = 0
  const end = parseInt(target)
  const range = end - start
  const startTime = performance.now()

  const updateCounter = (currentTime) => {
    const elapsed = currentTime - startTime
    const progress = Math.min(elapsed / duration, 1)

    const current = Math.floor(progress * range)
    element.textContent = prefix + current + suffix

    if (progress < 1) {
      requestAnimationFrame(updateCounter)
    } else {
      element.textContent = prefix + target + suffix
    }
  }

  requestAnimationFrame(updateCounter)
}

// References to counter elements
const studentsCounter = ref(null)
const testsCounter = ref(null)
const successCounter = ref(null)
const countriesCounter = ref(null)

// Initialize counters on component mount
onMounted(() => {
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        animateCounter(studentsCounter.value, '2.4', 2000, '', 'M+')
        animateCounter(testsCounter.value, '5.7', 2000, '', 'M+')
        animateCounter(successCounter.value, '98', 2000, '', '%')
        animateCounter(countriesCounter.value, '50', 2000, '', '+')
        observer.disconnect()
      }
    })
  })

  observer.observe(studentsCounter.value)
})
</script>
