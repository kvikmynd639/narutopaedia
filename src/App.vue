<template>
  <v-app>
    <v-main>
      <v-container>
        <character-list @characterSelected="selectCharacter"></character-list>
        <character-detail :character="selectedCharacter"></character-detail>
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
import CharacterList from './components/CharacterList.vue';
import CharacterDetail from './components/CharacterDetail.vue';

export default {
  name: 'App',
  components: {
    CharacterList,
    CharacterDetail
  },
  data() {
    return {
      selectedCharacter: null
    };
  },
  methods: {
    selectCharacter(character) {
      this.selectedCharacter = character;
    }
  }
};
</script>

<style>
/* Add any global styles here */
</style>
