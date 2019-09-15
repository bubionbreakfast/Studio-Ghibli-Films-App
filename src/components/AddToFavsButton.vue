<template lang="html">
  <div>
    <button v-on:click="handleClick">Add this Film to Your List</button>
    <button v-if="isFavourite" v-on:click="removeFavourite">
      Remove from Favourites
    </button>
  </div>
</template>

<script>

import { eventBus } from '../main.js'
export default {
  name: 'film-fav',
  props: ['film', 'isFavourite'],
  methods: {
    handleClick(){
      eventBus.$emit('fav-list', this.film)
    },
    removeFavourite() {
      eventBus.$emit("favourite-removed", this.film);
    }
  }
}
</script>

<style lang="css" scoped>
</style>
