<template>
  <div id="app">
    <h1>Welcome to Studio Ghilbi.. the App</h1>
    <img src="./assets/images.png" />
    <p>Select a film to see details, and add it to your own fav's list</p>
    <section>
    <div id="content-left">
      <film-list :films="films" />
      <film-detail :film="selectedFilm" />
    </div>
    <div id="content-right">
      <fav-list :favFilms="favFilms" />
    </div>
  </section>
  </div>
</template>

<script>
import FilmList from './components/FilmList.vue'
import FilmDetail from './components/FilmDetail.vue'
import FavFilms from './components/FavFilms.vue'

import { eventBus } from './main.js'


export default {
  name: 'app',
  data(){
    return {
      films: [],
      selectedFilm: null,
      favFilms: [],
    }
  },
  mounted(){
    fetch('https://ghibliapi.herokuapp.com/films')
    .then(res => res.json())
    .then(films => this.films = films)

    eventBus.$on('selected-film', (film) => {
      this.selectedFilm = film
    })
    eventBus.$on('fav-list', (film) => {
      this.favFilms.push(film)
    })
  },
  components: {
    "film-list": FilmList,
    "film-detail": FilmDetail,
    "fav-list": FavFilms
  }
}
</script>

<style lang="css" scoped>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 30px;
}

section {
  display: flex;

}

#content-left {
  /* width: 45%; */
}
#content-right {
  /* float: right; */
  width: 100%;
}
</style>
