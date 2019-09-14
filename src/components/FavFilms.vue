<template lang="html">
  <div>
    <li v-for="film in favFilms" value="film">{{ film.title }}</li>
  </div>
</template>

<script>

import { eventBus } from '../main.js'

export default {
  name: 'fav-list',
  props: ['favFilms']
}
</script>

<style lang="css" scoped>
</style>
