<template>
  <div>
    <CharacterList :characters="characters" @select-character="selectCharacter" />
    <CharacterDetail :character="selectedCharacter" />
  </div>
</template>

<script>
import axios from 'axios';
import CharacterList from './components/CharacterList.vue';
import CharacterDetail from './components/CharacterDetail.vue';

export default {
  components: {
    CharacterList,
    CharacterDetail
  },
  data() {
    return {
      characters: [],
      selectedCharacter: null
    };
  },
  created() {
    axios.get('https://narutodb.xyz/api/character?page=1&limit=20')
      .then(response => {
        this.characters = response.data;
      })
      .catch(error => {
        console.error('Error fetching characters:', error);
      });
  },
  methods: {
    selectCharacter(character) {
      this.selectedCharacter = character;
    }
  }
};
</script>
