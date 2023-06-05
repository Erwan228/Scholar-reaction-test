<template>
<h1>Scholar Reaction Timer</h1>
<button @click="start">Play</button>
</template>

<script>

export default {
  name: 'App',
  components: {  },
  data() {
    return{
      isPlaying: false,
      delay: null,
    }
  },
  methods: {
    start() {
      
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #444;
  margin-top: 60px;
}
</style>
