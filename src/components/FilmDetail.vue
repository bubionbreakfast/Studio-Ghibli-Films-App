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
  </div>
</template>

<script>
export default {
  name: "film-detail",
  props: ['film']
}
</script>

<style lang="css" scoped>
#film-detail {
  height: 250px;
  width: 45%;
  display: flex;
  flex-wrap: wrap;
  border: 1px solid black;
  overflow-y: scroll;
  padding: 5px;
}
</style>
