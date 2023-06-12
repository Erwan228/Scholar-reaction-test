<template>
<h1>Scholar Reaction Timer</h1>
<p>A test of your reflexes</p>
<button @click="start" :disabled="isPlaying">Play</button>
<Block v-if="isPlaying" :delay="delay" @end="endGame"/>
<Resaults v-if="showResults" :score="score"/>
<!-- <p v-if="showResults">Reaction time: {{ score }}ms</p> -->

</template>

<script>
import Block from './components/Block.vue'
import Resaults from './components/Resaults.vue'
export default {
  name: 'App',
  components: { Block, Resaults },
  data() {
    return{
      isPlaying: false,
      delay: null,
      score: null,
      showResults: false,
    }
  },
  methods: {
    start() {
      this.delay = 2000 + Math.random() * 5000 
      this.isPlaying = true
      this.showResults = false
    },
    endGame(reactionTime){
      this.score = reactionTime
      this.isPlaying = false
      this.showResults = true
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

*{
  user-select: none;
}
button{
  background: #0faf87;
  color: white;
  border: none;
  padding: 8px 16px;
  border-radius: 4px;
  font-size: 16px;
  letter-spacing: 1px;
  cursor: pointer;
  margin: 10px;
}
button[disabled]{
  opacity: 0.2;
  cursor: not-allowed;
}
</style>
