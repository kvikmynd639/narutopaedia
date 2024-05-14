<template>
    <v-container v-if="character">
      <v-row>
        <v-col cols="12">
          <v-card>
            <v-card-title>{{ character.name }}</v-card-title>
            <v-card-text>
              <strong>Age:</strong> {{ character.age }}<br>
              <strong>Gender:</strong> {{ character.gender }}<br>
              <strong>Occupation:</strong> {{ character.occupation }}<br>
              <strong>Description:</strong> {{ character.description }}
            </v-card-text>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </template>
  
  <script>
  export default {
    name: 'CharacterDetail',
    props: ['character']
  };
  </script>
  
  <style scoped>
  /* Add any component-specific styles here */
  </style>
  