<template lang="html">
  <div v-if="films">
    <ul>
      <li v-for="(film, index) in films" :film="film" :key="index">{{film.title}}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'film-list',
  props: ['film', 'films']
}
</script>

<style lang="css" scoped>
</style>
