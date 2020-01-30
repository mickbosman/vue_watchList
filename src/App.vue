<template>
  <div id="app">
    <Header />
    <AddFilm />
      <Films v-bind:films="films" v-on:del-film="deleteFilm" />
  </div>
</template>

<script>
import Header from './components/layout/Header';
import Films from './components/Films';
import AddFilm from './components/AddFilm';

export default {
  name: 'app',
  components: {
    Header,
    Films,
    AddFilm
  },
  data () {
    return {
      films: [
        {
          id: 1,
          title: "Film One",
          completed: false
        },
        {
          id: 2,
          title: "Fiml Two",
          completed: false
        },
        {
          id: 3,
          title: "Film Three",
          completed: false
        }
      ]
    }
  },
  methods: {
    deleteFilm(id) {
        this.films = this.films.filter(film => film.id !== id);
    }
  }
}
</script>

<style>
 *{
 box-sizing: border-box;
 margin: 0;
 padding: 0;
 }

 body {
 font-family: Arial, Helvetica, sans-serif;
 ling-height: 1.4;
 }
</style>
