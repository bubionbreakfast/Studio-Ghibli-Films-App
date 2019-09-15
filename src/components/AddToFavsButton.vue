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

button {
  padding: 10px;
  font: bold 11px Futura;
  text-decoration: none;
  background-color: #EEEEEE;
  color: #333333;
  padding: 2px 6px 2px 6px;
  border-top: 1px solid #CCCCCC;
  border-right: 1px solid #333333;
  border-bottom: 1px solid #333333;
  border-left: 1px solid #CCCCCC;
}
</style>
