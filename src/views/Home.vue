<template>
  <div id="app">
    <AddFilm v-on:add-film="addFilm"/>
      <Films v-bind:films="films" v-on:del-film="deleteFilm" />
  </div>
</template>

<script>
import Films from '../components/Films';
import AddFilm from '../components/AddFilm';
import axios from 'axios';

export default {
  name: 'Home',
  components: {
    Films,
    AddFilm
  },
  data () {
    return {
      films: []
    }
  },
  methods: {
    deleteFilm(id) {
      axios.delete (`https://jsonplaceholder.typicode.com/todos/${id}`)

        this.films = this.films.filter(film => film.id !== id);
    },
    addFilm(newFilm) {
      const { title, completed } = newFilm;

      axios.post('https://jsonplaceholder.typicode.com/todos', {
      title,
      completed
    })
      .then(res => this.films = [...this.films, res.data])
      // .catch(err => console.log(err));


      this.films = [...this.films, newFilm];
    }
  },
  created() {
    axios.get('https://jsonplaceholder.typicode.com/todos?_limit=5')
    .then(res => this.films = res.data)
    // .catch(err => console.log(err));
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

 .btn {
   display: inline-block;
   border: none;
   background: #555;
   color: #fff;
   padding: 7px 20px;
   cursor: pointer;
 }

 .btn hover {
   background: #666;
 }
</style>
