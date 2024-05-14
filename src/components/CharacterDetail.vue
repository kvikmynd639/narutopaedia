<template>
    <div v-if="character">
      <h2>{{ character.name }}</h2>
      <img :src="character.images" alt="Character Image" style="max-width: 200px;">
      <!-- Display other character details as needed -->
    </div>
    <p v-else>No character selected</p>
  </template>
  
  <script>
  export default {
    name: 'CharacterDetail',
    props: {
      character: {
        type: Object,
        default: null
      }
    }
  };
  </script>
  