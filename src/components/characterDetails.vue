<template>
  <div>
      <h1>{{character.name}}</h1>
      <h2>Species: {{character.species}}</h2>
      <h2>Gender: {{character.gender}}</h2>
      <h2>Origin: {{character.origin.name}}</h2>

  </div>

</template>

<script>
import { eventBus } from '../main.js'
export default {
    name: 'character-details',
    props: ['character']
}
</script>

<style>

</style>