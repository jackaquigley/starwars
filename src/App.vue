<template>
  <div class="">
    <film-list v-if="films.length" :films="films"></film-list>
  </div>
</template>

<script>
import FilmList from './components/FilmList.vue'
import {eventBus} from './main.js'

export default {
  data() {
    return {
      films: []
    }
  },
  components: {
    'film-list': FilmList
  },
  mounted(){
  fetch('https://swapi.dev/api/films/')
  .then(res => res.json())
  .then(data => this.films = data.results)
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
