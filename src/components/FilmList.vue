<template lang="html">
<section>
    <form v-on:submit.prevent>
      <div class="listWrapper">
        <label>Choose a Film: </label>
      <select
       v-on:change="handelSelect"
       v-model="selectedFilm">
        <option disabled value="">Select a Film</option>
        <option value="Select a Film">--Select--</option>
        <option v-for="film in films"
         :value="film"
         >{{ film.title }}</option>
      </select>
    </div>
    </form>
  </section>
</template>

<script>

import { eventBus } from '../main.js'

export default {
  name: "film-list",
  data() {
    return {
      selectedFilm: {}
    }
  },
  props: ['films'],
  methods: {
    handelSelect(){
      eventBus.$emit('selected-film', this.selectedFilm)
    }
  }
}
</script>

<style lang="css" scoped>
section {
  display: flex;
  justify-content: space-around;
}
.listWrapper {
    /* width: 45%; */
    /* height: 550px; */
    /* min-height: 550px; */
    /* overflow-y: scroll; */
    /* display: flex; */
    /* flex-wrap: wrap; */
    /* display: inline-flex; */
  }

</style>
