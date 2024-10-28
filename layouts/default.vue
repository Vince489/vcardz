<template>
  <div class="flex flex-col min-h-screen">
    <NavBar />
    <div class="flex-grow pt-16 bg-gray-600 text-gray-200">
      <slot />
    </div>
  </div>
</template>
