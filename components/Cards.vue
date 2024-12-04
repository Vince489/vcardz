<template>
  <div class="template-selection-container">
    <!-- Step Indicator -->
    <div class="step-indicator flex items-center mb-4">
      <div class="bg-black text-white px-2 py-1 rounded-full mr-2">STEP 1</div>
      <p class="text-lg font-semibold">Choose a template</p>
    </div>
    
    <!-- Template Options Container -->
    <div class="template-options flex justify-center space-x-4">
      <div
        v-for="(template, index) in templates"
        :key="index"
        @click="selectTemplate(index)"
        :class="['template-card', selectedTemplate === index ? 'border-blue-500' : 'border-transparent']"
        class="relative max-w-xs bg-white rounded-lg shadow-lg border-4 transition-all cursor-pointer"
      >
        <img :src="template.image" alt="Template Preview" class="rounded-lg" />

        <!-- Save to Contacts Button on each template -->
        <button
          class="absolute bottom-4 right-4 px-3 py-2 bg-blue-500 text-white rounded-full hover:bg-blue-600 shadow-lg"
        >
          Save to contacts
        </button>
      </div>
    </div>

    <!-- Learn more link -->
    <div class="flex justify-center mt-4">
      <a href="#" class="text-blue-500 underline">Learn how to track data with dynamic QR</a>
    </div>
  </div>
</template>

<script>
export default {
  name: 'TemplateSelection',
  data() {
    return {
      selectedTemplate: null,
      templates: [
        {
          id: 1,
          image: '/path/to/template1.png', // Replace with actual image paths
          name: 'Template 1',
        },
        {
          id: 2,
          image: '/path/to/template2.png',
          name: 'Template 2',
        },
        {
          id: 3,
          image: '/path/to/template3.png',
          name: 'Template 3',
        },
        {
          id: 4,
          image: '/path/to/template4.png',
          name: 'Template 4',
        },
        {
          id: 5,
          image: '/path/to/template5.png',
          name: 'Template 5',
        },
      ],
    };
  },
  methods: {
    selectTemplate(index) {
      this.selectedTemplate = index;
      // Emit the selected template ID to the parent component if needed
      this.$emit('templateSelected', this.templates[index]);
    },
  },
};
</script>

<style scoped>
.template-selection-container {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.template-options {
  display: flex;
  justify-content: center;
  gap: 1rem;
  overflow-x: auto;
  padding: 1rem;
}

.template-card {
  position: relative;
  width: 180px;
  cursor: pointer;
  transition: transform 0.2s ease;
}

.template-card:hover {
  transform: scale(1.05);
}

.step-indicator {
  display: flex;
  align-items: center;
}

button {
  z-index: 10;
}
</style>
