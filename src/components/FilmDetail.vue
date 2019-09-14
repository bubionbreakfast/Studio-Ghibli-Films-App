<template lang="html">
  <div id="flex-detail" v-if="film">
    <div id="film-detail">
      <h1>{{ film.title }}</h1>
      <ul>
        <h2>Director: {{ film.director }}</h2>
        <h2>Producer: {{ film.producer }}</h2>
        <h2>Release Date: {{ film.release_date }}</h2>
      </ul>
      <hr>

      <h2>Rt Score: {{ film.rt_score }}</h2>
      <!-- <h3>Rt Score: {{ film.people }}</h3> -->

      <p>Description: {{ film.description }}</p>
      <film-fav :film="film" />
    </div>
  </div>
</template>

<script>

import AddToFavsButton from './AddToFavsButton.vue'
import { eventBus } from '../main.js'

export default {
  name: "film-detail",
  props: ['film'],
  components: {
    "film-fav": AddToFavsButton
  }


}
</script>

<style lang="css" scoped>
#flex-detail {
  display: flex;
  display: inline-flex;
  flex-direction: row;
}
#film-detail {
  height: 450px;
  width: 45%;
  display: flex;
  flex-wrap: wrap;
  border: 1px solid black;
  overflow-y: scroll;
  padding: 10px;
  margin: 0 auto;
}
</style>
