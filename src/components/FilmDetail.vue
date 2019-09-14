<template lang="html">
  <div id="film-detail" v-if="film">
    <h2>Title: {{ film.title }}</h2>
    <hr>
    <h5>Director: {{ film.director }}</h5>
    <h3>Producer: {{ film.producer }}</h3>
    <h3>Release Date: {{ film.release_date }}</h3>
    <h3>Rt Score: {{ film.rt_score }}</h3>
    <!-- <h3>Rt Score: {{ film.people }}</h3> -->

    <p>Description: {{ film.description }}</p>
    <film-fav :film="film" />
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
#film-detail {
  height: 350px;
  width: 45%;
  display: flex;
  flex-wrap: wrap;
  border: 1px solid black;
  overflow-y: scroll;
  padding: 5px;
}
</style>
