<template>
  <div class="px-2 lg:px-6 max-w-screen-lg mx-auto">
    <!-- Navbar container -->
    <nav id="Navbar" class="bg-[rgb(47,118,176)] fixed inset-x-0 z-50">
      <div class="flex justify-between items-center py-3 px-4 md:px-48">
        <!-- Left side with plain text logo -->
        <div>
          <a href="/" class="text-white font-sans font-bold text-lg">LOGO</a>
        </div>
        
        <!-- Main navigation links for larger screens -->
        <div class="hidden md:flex space-x-6">
          <a href="/#about" class="text-gray-100 font-semibold">About</a>
          <a href="/#contact" class="text-gray-100 font-semibold">Contact</a>
        </div>

        <!-- Right side with Log In and Register buttons -->
        <div class="hidden md:flex items-center space-x-4">
          <a href="/#login" class="text-gray-100 font-semibold">Log In</a>
          <a href="/#register" class="px-4 py-1 border border-white text-gray-100 rounded hover:bg-white hover:text-[#1e7fce] transition">
            REGISTER
          </a>
        </div>

        <!-- Mobile menu button -->
        <button @click="toggleMenu" class="text-gray-100 md:hidden">
          <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6">
            <path stroke-linecap="round" stroke-linejoin="round" d="M3.75 6.75h16.5M3.75 12h16.5m-16.5 5.25h16.5" />
          </svg>
        </button>
      </div>

      <!-- Mobile sidebar menu -->
      <div 
        :class="{ 'translate-x-0': menuOpen, 'translate-x-full': !menuOpen }" 
        class="fixed right-0 top-0 h-full w-80 bg-[#205785] border-l border-gray-500 rounded-tl-xl rounded-bl-xl transition-transform duration-300 ease-in-out transform md:hidden z-40 overflow-y-auto"
      >
        <div class="px-4 py-4 flex flex-col">
          <a @click="toggleMenu" href="/" class="text-gray-300 hover:bg-gray-600 py-2 px-4 rounded">Home</a>
          <a @click="toggleMenu" href="/#about" class="text-gray-300 hover:bg-gray-600 py-2 px-4 rounded">About</a>
          <a @click="toggleMenu" href="/#contact" class="text-gray-300 hover:bg-gray-600 py-2 px-4 rounded">Contact</a>
          <a @click="toggleMenu" href="/#login" class="text-gray-300 hover:bg-gray-600 py-2 px-4 rounded">Log In</a>
          <a @click="toggleMenu" href="/#register" class="px-4 py-1 border border-white text-gray-300 rounded hover:bg-white hover:text-[#1e7fce] transition">
            REGISTER
          </a>
        </div>
      </div>
    </nav>

    <!-- Overlay for mobile sidebar -->
    <div 
      v-if="menuOpen" 
      @click="toggleMenu" 
      class="fixed inset-0 bg-black opacity-50 md:hidden z-30"
    ></div>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const menuOpen = ref(false);
function toggleMenu() {
  menuOpen.value = !menuOpen.value;
}
</script>
