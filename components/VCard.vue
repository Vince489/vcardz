<template>
  <div class="relative w-full max-w-sm mx-auto bg-white rounded-lg shadow-lg overflow-hidden">
    <!-- Profile Image Section -->
    <div class="bg-blue-500 p-6 flex flex-col items-center">
      <div class="w-24 h-24 rounded-full bg-white overflow-hidden border-4 border-white mb-4">
        <img
          src="https://via.placeholder.com/100"
          alt="Profile Picture"
          class="object-cover w-full h-full"
        />
      </div>
      <h2 class="text-white text-lg font-semibold">Your Full Name</h2>
      <p class="text-white text-sm opacity-75">Position - Company Name</p>
    </div>

    <!-- Contact Information Section -->
    <div class="p-6 pb-20"> <!-- Add padding-bottom to prevent overlap with button -->
      <p class="text-gray-600 text-sm mb-4 text-center">
        Personal Description goes here. A few lines about this individual and their role.
      </p>

      <!-- Contact Buttons with Spacing -->
      <div class="flex justify-between space-x-2 mb-4">
        <button
          class="flex items-center justify-center w-1/3 p-2 text-blue-500 bg-blue-100 rounded-lg hover:bg-blue-200"
        >
          <svg class="w-5 h-5 mr-1" xmlns="http://www.w3.org/2000/svg" fill="currentColor" viewBox="0 0 24 24">
            <path d="M4.75 3a.75.75 0 000 1.5H6.5v14.25a.75.75 0 001.5 0V4.5H11v14.25a.75.75 0 001.5 0V4.5h3.75a.75.75 0 000-1.5H4.75z" />
          </svg>
          Phone
        </button>
        <button
          class="flex items-center justify-center w-1/3 p-2 text-blue-500 bg-blue-100 rounded-lg hover:bg-blue-200"
        >
          <svg class="w-5 h-5 mr-1" xmlns="http://www.w3.org/2000/svg" fill="currentColor" viewBox="0 0 24 24">
            <path d="M3 8c0-2.7 2.8-5 6-5s6 2.3 6 5-2.8 5-6 5-6-2.3-6-5zm9 5c1.6 0 3.2-.8 4.2-2C14.5 12.2 13 13 11 13H3.4l.5-.5c1.1-1.2 3.5-2.5 6.1-2.5 0-.3 0-.7-.1-1 0-3.1-2.5-5.5-5.5-5.5S1 6.9 1 10s2.5 5.5 5.5 5.5h6.5z" />
          </svg>
          Email
        </button>
        <button
          class="flex items-center justify-center w-1/3 p-2 text-blue-500 bg-blue-100 rounded-lg hover:bg-blue-200"
        >
          <svg class="w-5 h-5 mr-1" xmlns="http://www.w3.org/2000/svg" fill="currentColor" viewBox="0 0 24 24">
            <path d="M18 6h-3.6c-.8 0-1.5.3-2 .8l-3.4 3.4c-.5.5-.8 1.2-.8 2V18c0 .6.4 1 1 1h4.6c.8 0 1.5-.3 2-.8l3.4-3.4c.5-.5.8-1.2.8-2V7c0-.6-.4-1-1-1zm0 5.6l-2.6 2.6c-.5.5-1.1.8-1.7.8h-4.6V7.4l2.6-2.6H18v6.8z" />
          </svg>
          Website
        </button>
      </div>

      <!-- Additional Info -->
      <div class="text-gray-600 text-sm">
        <p><strong>Mobile Phone (Work):</strong> +1 234 567 890</p>
        <p><strong>Phone:</strong> +1 098 765 4321</p>
        <p><strong>Email:</strong> example@email.com</p>
        <p><strong>Organization:</strong> Company XYZ</p>
      </div>
    </div>

    <!-- Save to Contacts Button in Bottom-Right of the Card -->
    <button
      class="absolute bottom-4 right-4 px-4 py-2 bg-blue-500 text-white rounded-full hover:bg-blue-600 shadow-lg z-10"
    >
      Save to Contacts
    </button>
  </div>
</template>

<script>
export default {
  name: 'ContactCard',
};
</script>

<style scoped>
/* Add any custom styling here if needed */
</style>
