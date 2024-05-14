<template>
    <div v-if="character" class="max-w-md mx-auto mt-8">
      <div class="bg-white shadow-lg rounded-lg overflow-hidden">
        <img v-if="character.images.length" :src="character.images[0]" alt="Character Image" class="w-full h-48 object-cover">
        <div class="p-6">
          <h2 class="text-xl font-semibold mb-2">{{ character.name }}</h2>
          <div v-if="character.info" class="mb-4">
            <h3 class="text-lg font-semibold mb-2">Info</h3>
            <ul>
              <li v-for="(value, key) in character.info" :key="key" class="text-sm"><strong>{{ key }}:</strong> {{ value }}</li>
            </ul>
          </div>
          <div v-if="character.about.length">
            <h3 class="text-lg font-semibold mb-2">About</h3>
            <ul>
              <li v-for="(about, index) in character.about" :key="index" class="text-sm">{{ about }}</li>
            </ul>
          </div>
        </div>
      </div>
    </div>
    <p v-else class="text-center mt-8">No character selected</p>
  </template>
  
  <script>
  export default {
    props: {
      character: {
        type: Object,
        default: null
      }
    }
  };
  </script>
  
  <style scoped>
  /* Add scoped styles here */
  </style>
  