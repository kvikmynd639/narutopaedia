<template>
  <v-container>
    <v-row>
      <v-col v-for="character in characters" :key="character.id" cols="12" md="4">
        <v-card @click="selectCharacter(character)">
          <v-card-title>{{ character.name }}</v-card-title>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: 'CharacterList',
  data() {
    return {
      characters: []
    };
  },
  created() {
    fetch('https://naruto-api.herokuapp.com/api/v1/characters')
      .then(response => response.json())
      .then(data => {
        this.characters = data;
      });
  },
  methods: {
    selectCharacter(character) {
      this.$emit('characterSelected', character);
    }
  }
};
</script>

<style scoped>
/* Add any component-specific styles here */
</style>
