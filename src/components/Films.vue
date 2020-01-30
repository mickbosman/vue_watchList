<template>
  <div>
    <div v-bind:key="film.id" v-for="film in films">
      <FilmItem v-bind:film="film" v-on:del-film="$emit('del-film',
      film.id)" />
  </div>
</div>
</template>

<script>
import FilmItem from './FilmItem.vue';

  export default {
    name: "Films",
    components: {
      FilmItem
    },
    props: ["films"]
  }
</script>

<style scoped>

</style>
