<script setup>
import Block from './components/Block.vue';
</script>

<script>
export default {
  data() {
    return {
      isPlaying: false,
      showResult: false,
      delay: null,
      score: null,
    };
  },
  methods: {
    start() {
      this.delay = 10 + Math.random() * 2500;
      this.isPlaying = true;
      console.log(this.delay);
      this.showResult = false;
    },
    endGame(reactionTime) {
      this.score = reactionTime;
      this.isPlaying = false;
      this.showResult = true;
    },
  },
};
</script>

<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <h1>Andy Lovely Timer</h1>
  <button @click="start" :disabled="isPlaying">play</button>
  <Block v-if="isPlaying" :delay="delay" @end="endGame" />
  <p v-if="showResult">Reaction Time = {{ score }} ms</p>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
