<template lang="html">
  <div>
  <h1 v-if='film'>{{film.title}}</h1>
  <p>{{film.episode_id}}</p>
  <p>{{film.release_date}}</p>
  <p>{{film.director}}</p>
</div>
</template>

<script>
export default {
  name: 'film-detail',
  props: ['film']
}
</script>

<style lang="css" scoped>
</style>
