<template>
  <div class="flex flex-col items-center pt-4">
    <!-- Tabs Selector -->
    <div
      class="flex items-center justify-start flex-nowrap space-x-2 md:space-x-4 bg-blue-800 p-2 rounded-lg shadow-lg overflow-x-auto no-scrollbar w-full"
    >
      <button
        v-for="tab in tabs"
        :key="tab.value"
        @click="activeTab = tab.value"
        :class="[ 
          'flex items-center space-x-2 px-4 py-2 rounded-lg transition duration-300',
          activeTab === tab.value
            ? 'bg-white text-blue-800 shadow font-bold'
            : 'text-white hover:bg-blue-600',
        ]"
      >
        <icon :name="tab.icon" class="text-lg sm:text-xl md:text-2xl" />
        <span class="text-sm sm:text-base">{{ tab.label }}</span>
      </button>
    </div>

    <!-- Dynamic Tab Content -->
    <div class="mt-6 w-full max-w-3xl p-4 rounded-lg shadow bg-white">
      <!-- URL Content -->
      <div v-if="activeTab === 'url'">
        <div class="flex items-center mb-4">
          <span class="bg-blue-600 text-white px-3 py-1 rounded-full font-bold text-sm">STEP 1</span>
          <h2 class="ml-4 text-lg font-semibold text-gray-800">Enter the URL</h2>
        </div>

        <div class="mb-4">
          <input
            v-model="url"
            type="text"
            placeholder="https://www.mywebsite.com"
            class="w-full p-3 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-blue-500"
          />
          <p class="text-sm text-blue-600 mt-2">
            <a href="#" class="hover:underline">...or upload an image to extract the URL</a>
          </p>
        </div>

        <div class="flex items-center space-x-4 mb-6">
          <!-- Static QR -->
          <label
            :class="['flex items-center space-x-2 p-3 border rounded-md cursor-pointer transition', 
                    qrType === 'static' ? 'border-green-500' : 'border-gray-300']"
          >
            <input
              type="radio"
              value="static"
              v-model="qrType"
              class="hidden"
            />
            <span
              class="w-5 h-5 border-2 rounded-full flex items-center justify-center"
              :class="qrType === 'static' ? 'border-green-500 bg-green-500' : 'border-gray-300'"
            ></span>
            <span class="text-sm font-medium">Static QR</span>
          </label>

          <!-- Dynamic QR -->
          <label
            :class="['flex items-center space-x-2 p-3 border rounded-md cursor-pointer transition',
                    qrType === 'dynamic' ? 'border-green-500' : 'border-gray-300']"
          >
            <input
              type="radio"
              value="dynamic"
              v-model="qrType"
              class="hidden"
            />
            <span
              class="w-5 h-5 border-2 rounded-full flex items-center justify-center"
              :class="qrType === 'dynamic' ? 'border-green-500 bg-green-500' : 'border-gray-300'"
            ></span>
            <span class="text-sm font-medium">Dynamic QR</span>
          </label>
        </div>

        <div class="text-center">
          <button
            class="bg-gray-300 text-gray-600 px-6 py-2 rounded-md cursor-not-allowed"
            disabled
          >
            Generate QR code
          </button>
          <p class="text-sm text-gray-500 mt-2">
            We recommend creating a <span class="text-blue-600 font-medium">dynamic QR code</span> if you want to track performance and edit data even after printing.
          </p>
        </div>
      </div>

      <!-- Other Dynamic Content -->
      <p v-else-if="activeTab === 'vcard'">vCard content goes here...</p>
      <p v-else-if="activeTab === 'file'">File content goes here...</p>
      <p v-else-if="activeTab === 'image'">Image content goes here...</p>
      <p v-else-if="activeTab === 'video'">Video content goes here...</p>
      <p v-else-if="activeTab === 'audio'">Audio content goes here...</p>
      <p v-else-if="activeTab === 'contact'">Contact content goes here...</p>
      <p v-else-if="activeTab === 'calendar'">Calendar content goes here...</p>
      <p v-else-if="activeTab === 'location'">Location content goes here...</p>
      <p v-else-if="activeTab === 'bookmark'">Bookmark content goes here...</p>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";

const activeTab = ref("url");
const url = ref("");
const qrType = ref("static");

const tabs = [
  { value: "url", label: "URL", icon: "ph-link-simple" },
  { value: "vcard", label: "vCard", icon: "ph-user-circle" },
  { value: "file", label: "File", icon: "ph-file-text" },
  { value: "image", label: "Image", icon: "ph-image" },
  { value: "video", label: "Video", icon: "ph-video" },
  { value: "audio", label: "Audio", icon: "ph-music-note" },
  { value: "contact", label: "Contact", icon: "ph-address-book" },
  { value: "calendar", label: "Calendar", icon: "ph-calendar" },
  { value: "location", label: "Location", icon: "ph-map-pin" },
  { value: "bookmark", label: "Bookmark", icon: "ph-bookmark" },
];
</script>
