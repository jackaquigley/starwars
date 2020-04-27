<template lang="html">
  <div if="characters">
<ul>
  <li v-for="(character, index) in characters" :key="index" :characters="characters">
    <p>{{character.name}}</p>
    <p>{{character.height}}cm</p>
  </li>
</ul>
</div>
</template>

<script>
export default {
  name: 'character-list',
  props: ['characters', 'character']
}
</script>

<style lang="css" scoped>
</style>
