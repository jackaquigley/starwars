<template>
  <div class="">
    <film-list v-if="films.length" :films="films"></film-list>
    <film-detail :film='selectedFilm'></film-detail>
  </div>
</template>

<script>
import FilmDetail from './components/FilmDetail.vue'
import FilmList from './components/FilmList.vue'
import {eventBus} from './main.js'


export default {
  data() {
    return {
      films: [],
      selectedFilm: null
    }
  },
  components: {
    'film-list': FilmList,
    'film-detail': FilmDetail
  },
  mounted(){
  fetch('https://swapi.dev/api/films/')
  .then(res => res.json())
  .then(data => this.films = data.results)

  eventBus.$on('film-selected', (film) => {this.selectedFilm = film})
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
