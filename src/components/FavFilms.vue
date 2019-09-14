<template lang="html">
  <div id="fav-list-view">
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
#fav-list-view {
  height: 450px;
  width: 45%;
  display: flex;
  flex-wrap: wrap;
  border: 1px dashed black;
  overflow-y: scroll;
  padding: 5px;
}
</style>
