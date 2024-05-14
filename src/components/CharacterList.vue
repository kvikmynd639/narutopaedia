<template>
  <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-4 px-4 py-2">
    <h1 class="col-span-full text-center text-3xl font-bold mb-6">Naruto Characters</h1>
    <div v-for="character in characters" :key="character.id" @click="selectCharacter(character)" class="hover:bg-gray-200 bg-white rounded-lg shadow-lg cursor-pointer transition duration-300">
      <div class="relative overflow-hidden rounded-t-lg">
        <img v-if="character.images.length" :src="character.images[0]" alt="Character Img" class="w-full h-64 object-cover">
        <div class="absolute bottom-0 left-0 bg-black bg-opacity-75 p-2 w-full">
          <p class="text-white text-lg font-semibold">{{ character.name }}</p>
        </div>
      </div>
      <div class="p-4">
        <ul class="text-sm">
          <li v-for="(value, key) in character.info" :key="key" class="mb-2"><strong>{{ key }}:</strong> {{ value }}</li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CharacterList',
  props: {
    characters: {
      type: Array,
      default: () => []
    }
  },
  methods: {
    selectCharacter(character) {
      this.$emit('select-character', character);
    }
  }
};
</script>

<style>
/* Add your styles here */
</style>
