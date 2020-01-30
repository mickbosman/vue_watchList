<template>
  <div class="film-item" >
    <p>{{film.title}}</p>
  </div>
</template>

<script>
export default {
  name: "FilmItem",
  props: ["film"]
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
