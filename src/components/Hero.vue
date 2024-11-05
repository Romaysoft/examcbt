<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <div class="relative overflow-hidden">
    <!-- Gradient Background -->
    <div class="absolute inset-0 bg-gradient-to-br from-blue-50 via-indigo-50 to-purple-50"></div>

    <!-- Pattern Overlay -->
    <div
      class="absolute inset-0"
      :style="{
        backgroundImage: `url('data:image/svg+xml,%3Csvg width=\'60\' height=\'60\' viewBox=\'0 0 60 60\' xmlns=\'http://www.w3.org/2000/svg\'%3E%3Cg fill=\'none\' fill-rule=\'evenodd\'%3E%3Cg fill=\'%236366f1\' fill-opacity=\'0.08\'%3E%3Cpath d=\'M36 34v-4h-2v4h-4v2h4v4h2v-4h4v-2h-4zm0-30V0h-2v4h-4v2h4v4h2V6h4V4h-4zM6 34v-4H4v4H0v2h4v4h2v-4h4v-2H6zM6 4V0H4v4H0v2h4v4h2V6h4V4H6z\'/%3E%3C/g%3E%3C/g%3E%3C/svg%3E')`
      }"
    ></div>

    <!-- Animated Blobs -->
    <div class="absolute top-20 left-0 w-72 h-72 bg-purple-300 rounded-full mix-blend-multiply filter blur-xl opacity-20 animate-blob"></div>
    <div class="absolute top-0 right-4 w-72 h-72 bg-yellow-300 rounded-full mix-blend-multiply filter blur-xl opacity-20 animate-blob animation-delay-2000"></div>
    <div class="absolute -bottom-8 left-20 w-72 h-72 bg-blue-300 rounded-full mix-blend-multiply filter blur-xl opacity-20 animate-blob animation-delay-4000"></div>

    <!-- Floating Particles -->
    <div class="absolute inset-0">
      <div class="particle bg-blue-700"></div>
      <div class="particle bg-red-700"></div>
      <div class="particle bg-yellow-700"></div>
      <div class="particle bg-green-700"></div>
      <div class="particle bg-purple-700"></div>
      <div class="particle bg-pink-700"></div>
    </div>

    <!-- Content -->
    <div class="relative max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex flex-col-reverse lg:flex-row items-center py-24 lg:py-32">
        <!-- Text Content -->
        <div class="lg:w-1/2 mt-10 lg:mt-0 lg:pr-12">
          <h1 class="text-4xl lg:text-5xl font-bold text-gray-900 leading-tight">
            Transform Your Exam Experience with Modern CBT
          </h1>
          <p class="mt-6 text-xl text-gray-600">
            Experience seamless computer-based testing with our advanced platform. Practice, learn, and excel in your examinations with confidence.
          </p>
          <div class="mt-10 flex flex-col sm:flex-row gap-4">
            <button class="px-8 py-3 bg-blue-600 text-white rounded-md hover:bg-blue-700 font-medium">
              Start Practice Test
            </button>
            <button class="px-8 py-3 border border-blue-600 text-blue-600 rounded-md hover:bg-blue-50 font-medium">
              Learn More
            </button>
          </div>
          <div class="mt-10 flex items-center gap-6">
            <div class="flex flex-col">
              <span class="text-2xl font-bold text-gray-900">10K+</span>
              <span class="text-gray-600">Active Students</span>
            </div>
            <div class="flex flex-col">
              <span class="text-2xl font-bold text-gray-900">50+</span>
              <span class="text-gray-600">Exam Types</span>
            </div>
            <div class="flex flex-col">
              <span class="text-2xl font-bold text-gray-900">98%</span>
              <span class="text-gray-600">Success Rate</span>
            </div>
          </div>
        </div>

        <!-- Image -->
        <div class="lg:w-1/2">
          <img
            src="../assets/examcbt.png"
            alt="Online Examination Platform"
            class="w-full h-auto object-cover"
          >
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
/* Blob Animation */
.animate-blob {
  animation: blob 7s infinite;
}

.animation-delay-2000 {
  animation-delay: 2s;
}

.animation-delay-4000 {
  animation-delay: 4s;
}

@keyframes blob {
  0% {
    transform: translate(0px, 0px) scale(1);
  }
  33% {
    transform: translate(30px, -50px) scale(1.1);
  }
  66% {
    transform: translate(-20px, 20px) scale(0.9);
  }
  100% {
    transform: translate(0px, 0px) scale(1);
  }
}

/* Particle Animation */
.particle {
  position: absolute;
  width: 10px;
  height: 10px;
  border-radius: 50%;
  opacity: 0.3;
  pointer-events: none;
}

.particle:nth-child(1) {
  top: 20%;
  left: 20%;
  animation: floatingParticle 8s infinite;
}

.particle:nth-child(2) {
  top: 60%;
  left: 80%;
  animation: floatingParticle 10s infinite 1s;
}

.particle:nth-child(3) {
  top: 40%;
  left: 40%;
  animation: floatingParticle 7s infinite 2s;
}

.particle:nth-child(4) {
  top: 80%;
  left: 60%;
  animation: floatingParticle 9s infinite 3s;
}

.particle:nth-child(5) {
  top: 30%;
  left: 70%;
  animation: floatingParticle 11s infinite 4s;
}

.particle:nth-child(6) {
  top: 70%;
  left: 30%;
  animation: floatingParticle 6s infinite 5s;
}

@keyframes floatingParticle {
  0% {
    transform: translate(0, 0) rotate(0deg) scale(1);
  }
  25% {
    transform: translate(100px, -50px) rotate(90deg) scale(1.2);
  }
  50% {
    transform: translate(0, 100px) rotate(180deg) scale(0.8);
  }
  75% {
    transform: translate(-100px, 50px) rotate(270deg) scale(1.2);
  }
  100% {
    transform: translate(0, 0) rotate(360deg) scale(1);
  }
}
</style>
