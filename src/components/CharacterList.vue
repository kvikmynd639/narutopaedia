<template>
  <div class="grid grid-cols-4 gap-4 px-2 py-1">
    <h1 class="col-span-4 text-center text-2xl mb-4">Naruto Characters</h1>
    <div v-for="character in characters" :key="character.id" @click="selectCharacter(character)" class="hover:bg-gray-200 rounded p-4 cursor-pointer transition duration-300">
      <p class="text-lg font-semibold">{{ character.name }}</p>
      <img v-if="character.images.length" :src="character.images[0]" alt="Character Image" class="w-full h-48 object-cover">
      <ul>
            <li v-for="(value, key) in character.info" :key="key" class="text-sm"><strong>{{ key }}:</strong> {{ value }}</li>
        </ul>
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
