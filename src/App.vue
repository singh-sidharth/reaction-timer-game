<template>
  <h1>Ninja Reaction Timer</h1>
  <Results v-if="score" :score="score"/>
  <button @click="start" :disabled="isPlaying">play</button>
  <Block v-if="isPlaying" v-bind:delay="delay" @end="endGame"/>
</template>

<script>
import Block from './components/Block.vue';
import Results from './components/Results.vue';
export default {
  name: "App",
  components: {
    Block,
    Results
  },
  data(){
    return {
      isPlaying: false,
      delay: null,
      score: 0,
    }
  },
  methods:{
    start(){
      this.score = 0;
      this.delay = 2000 + Math.random()*3000;
      this.isPlaying = true;
    },
    endGame(reactionTime){
      this.score = reactionTime;
      this.isPlaying = false;
    }
  }
};
</script>

<style>
:root{
  --clr-primary: #0faf87;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
button{
  padding: 4px 16px;
  border: 1px solid var(--clr-primary);
  border-radius: 4px;
  background: none;
  text-transform: capitalize;
}
button:hover{
  background: #0faf80;
  color: white;
  cursor: pointer;
}
.clickable {
  cursor: pointer;
}
</style>
