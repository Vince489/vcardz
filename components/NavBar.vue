<template>
  <div class="px-2 lg:px-6 max-w-screen-lg mx-auto">
    <!-- Navbar container -->
    <nav id="Navbar" class="pt-1 z-40 bg-gray-500 fixed inset-x-0">
      <div class="px-4 pb-2 mx-auto">
        <div class="flex justify-between">
          <!-- Left side with logo and links -->
          <div class="flex space-x-4">
            <!-- Logo -->
            <div>
              <a href="/" class="flex items-center py-3 px-3 text-gray-300">
                <img src="" alt="Logo" class="h-8" />
              </a>
            </div>
            <!-- Main navigation -->
            <div class="hidden md:flex items-center space-x-3">
              <a href="/" class="font-semibold py-3 px-3 text-lg text-gray-100">Home</a>
              <a href="/#about" class="font-semibold py-3 px-3 text-lg text-gray-100">About</a>
              <a href="/#contact" class="font-semibold py-3 px-3 text-lg text-gray-100">Contact</a>
            </div>
          </div>
          <!-- Mobile menu button -->
          <div ref="menuBtn" class="text-gray-100 md:hidden flex items-center space-x-2">
            <button @click="toggleMenu" class="mobile-menu-button border border-gray-300 rounded-md p-1">
              <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6">
                <path stroke-linecap="round" stroke-linejoin="round" d="M3.75 6.75h16.5M3.75 12h16.5m-16.5 5.25h16.5" />
              </svg>
            </button>
          </div>
        </div>
      </div>

      <!-- Mobile menu -->
      <div 
        :class="{ 'transform translate-x-0': toggleMenuState, 'transform translate-x-full': !toggleMenuState }" 
        ref="mobileMenu" 
        class="bg-gray-700 mobile-menu md:hidden transition-transform duration-300 fixed right-0 top-0 h-full w-80 overflow-y-auto rounded-tl-xl rounded-bl-xl border-l border-gray-500"
      >
        <div class="px-4 py-4 flex flex-col">
          <a href="/" class="text-gray-300 hover:bg-gray-600 hover:rounded py-2 px-4">Home</a>
          <a href="/#about" class="text-gray-300 hover:bg-gray-600 hover:rounded py-2 px-4">About</a>
          <a href="/#contact" class="text-gray-300 hover:bg-gray-600 hover:rounded py-2 px-4">Contact</a>
        </div>
      </div>
    </nav>
  </div>
</template>

<script setup>
import { ref, onMounted, onBeforeUnmount } from 'vue';

const toggleMenuState = ref(false);
const menuBtn = ref(null);
const mobileMenu = ref(null);

function toggleMenu() {
  toggleMenuState.value = !toggleMenuState.value;
}

const handleClick = (e) => {
  if (mobileMenu.value && !menuBtn.value.contains(e.target)) {
    toggleMenuState.value = false;
  }
};

onMounted(() => {
  window.addEventListener("click", handleClick);
});

onBeforeUnmount(() => {
  window.removeEventListener("click", handleClick);
});
</script>

<style>
/* Optional styles for better layout */
</style>
