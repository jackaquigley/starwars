<template lang="html">
  <div>
  <h1 v-if='film'>{{film.title}}</h1>
  <p>{{film.episode_id}}</p>
  <p>{{film.release_date}}</p>
  <p>{{film.director}}</p>

  <character-list v-if="characters.length" :characters="characters"></character-list>
</div>
</template>

<script>

import CharacterList from './CharacterList.vue'


export default {
  name: 'film-detail',
  props: ['film'],
  components: {
    'character-list': CharacterList
  },
  data() {
    return {
      characters: []
    }
  },
  methods: {
    getCharacters() {
      const characterPromises = this.film.characters.map((characterData) => {
      return fetch(characterData).then(res => res.json())
  })
  Promise.all(characterPromises)
  .then(data => this.characters = data);
  }
},
mounted(){
  this.getCharacters();
},
watch:{
  film: function(){this.getCharacters();
      }
    }
  }
</script>

<style lang="css" scoped>
</style>
