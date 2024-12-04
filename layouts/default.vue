<!-- layouts/default.vue -->

<template>
  <div class="flex flex-col min-h-screen">
    <NavBar />
    <div class="flex-grow pt-14 bg-[#205785] text-gray-300">
      <slot />
    </div>
  </div>
</template>
