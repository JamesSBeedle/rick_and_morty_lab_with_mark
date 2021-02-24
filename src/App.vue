<template>
  <div id="app">
    <h1>Rick and Morty: A Character Sensational Selector</h1>
    <div>
      <character-list :characters="characterList"></character-list>
      <character-details :character="selectedCharacter"></character-details>
    </div>
    
  </div>
</template>

<script>
import characterDetails from './components/characterDetails';
import characterList from './components/characterList'

import { eventBus } from './main.js';


export default {
  name: 'App',
  data(){
    return{
    characterList: [],
    selectedCharacter: null
    };
  },
  mounted() {
    fetch('https://rickandmortyapi.com/api/character/')
    .then(res => res.json())
    .then(characters => this.characterList = characters.results)

    eventBus.$on('character-selected', (character) => {
      this.selectedCharacter = character
    })
  },
  components: {
    "character-list": characterList,
    "character-details": characterDetails
     }
}
</script>

<style>

</style>
