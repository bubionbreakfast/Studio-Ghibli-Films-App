<template lang="html">
  <div>
    <button v-on:click="handleClick">Add this Film to Your List</button>
  </div>
</template>

<script>

import { eventBus } from '../main.js'
export default {
  name: 'film-fav',
  props: ['film'],
  methods: {
    handleClick(){
      eventBus.$emit('fav-list', this.film)
    }
  }
}
</script>

<style lang="css" scoped>
</style>
