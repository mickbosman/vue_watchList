<template>
  <div>
    <form @submit="addFilm">
      <input type="text" v-model="title" name="title" placeholder="Klik hier om een film toe tevoegen">
      <input type="submit" value="submit" class="btn">
    </form>
  </div>
</template>

<script>
// import uuid from 'uuid';
export default {
  name: "AddFilm",
  data () {
    return {
      title: ''
    }
  },
  methods: {
    addFilm (e) {
      e.preventDefault();
      const newFilm = {
        title: this.title,
        completed: false
      }
      // Send up to perent
      this.$emit('add-film', newFilm);

      this.title = '';
    }
  }
}
</script>

<style scoped>
  form {
    display: flex;
  }

  input[type="text"] {
    flex: 10;
    padding: 5px;
    text-align: center;
    font-size: 30px
  }

  input [type="submit"] {
    flex: 2;
  }
</style>
