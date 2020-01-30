<template>
  <div class="film-item" v-bind:class="{'is-complete':film.completed}">
    <p>
      <input type="checkbox" v-on:change="markComplete">
      {{film.title}}
      <button @click="$emit('del-film', film.id)" class="del">X</button>
    </p>
  </div>
</template>

<script>
export default {
  name: "FilmItem",
  props: ["film"],
  methods: {
    markComplete() {
      this.film.completed = !this.film.completed;
    }
  }
}


</script>

<style scoped>
  .film-item {
    background: #f4f4f4;
    padding: 10px;
    border-bottom: 1px #ccc dotted;
  }

  .is-complete {
    text-decoration: line-through;
  }

  .del {
    background: #ff0000;
    color: #fff;
    border: none;
    padding: 5px 9px;
    border-radius: 50%;
    cursor: pointer;
    float: right;
  }
</style>
