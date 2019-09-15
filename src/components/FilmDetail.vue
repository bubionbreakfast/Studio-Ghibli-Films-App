<template lang="html">
  <div id="flex-detail" v-if="film">
    <div id="film-detail">
      <h2>{{ film.title }}</h2>
      <ul>
        <li>Director: {{ film.director }}</li>
        <li>Producer: {{ film.producer }}</li>
        <li>Release Date: {{ film.release_date }}</li>
        <li>Rt Score: {{ film.rt_score }}</li>
      </ul>
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
  width: 65%;
  display: flex;
  /* flex-wrap: wrap; */
  flex-direction: column;
  border: 1px solid black;
  overflow-y: scroll;
  padding: 10px;
  /* margin: 0 auto; */
}
li {
  display: inline;
  font: 13px Futura;
  padding-right: 10px;
}
</style>
