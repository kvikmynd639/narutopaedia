<template>
  <div>
    <h1>Naruto Characters</h1>
    <ul v-if="characters.length">
      <li v-for="character in characters" :key="character.id" @click="selectCharacter(character)">
        {{ character.name }}
      </li>
    </ul>
    <p v-else>No characters found</p>
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
