<template>
  <div id="app">
      <Films v-bind:films="films" />
  </div>
</template>

<script>
import Films from './components/Films';

export default {
  name: 'app',
  components: {
    Films
  },
  data () {
    return {
      films: [
        {
          id: 1,
          title: "Todo One",
          completed: false
        },
        {
          id: 2,
          title: "Todo Two",
          completed: true
        },
        {
          id: 3,
          title: "Todo Three",
          completed: false
        }
      ]
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
