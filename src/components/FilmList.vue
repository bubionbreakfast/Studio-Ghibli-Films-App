<template lang="html">

    <form v-on:submit.prevent>
      <div class="listWrapper">
      <select
       v-on:change="handelSelect"
       v-model="selectedFilm">
        <option disabled value="">Select a Film</option>
        <option v-for="film in films"
         :value="film"
         >{{ film.title }}</option>
      </select>
    </div>
    </form>
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
.listWrapper {
    /* width: 45%; */
    height: 550px;
    min-height: 550px;
    overflow-y: scroll;
    display: flex;
    /* flex-wrap: wrap; */
    display: inline-flex;
  }

</style>
