<template>
  <h1>Ninja Reaction Timer</h1>
  <button @click="startgame" :disabled="isPlaying">Play</button>
  <!-- Only Show block only if we are playing that's why we used v-if-->
  <!-- Binding some data into this because we want to pass in this property v-bind: or only : -->
  <Block  v-if="isPlaying" :delay="delay"/>
</template>

<script>
// Component imports
import Block from "./components/Block.vue";

export default {
  name: "App",
  components: {
    Block,
  },
  data() {
    return {
      isPlaying: false, // must be true to start the game
      delay: null, // must be in 20 sec
    };
  },
  methods: {
    startgame() {
      this.delay = 2000 + Math.random() * 5000; // Min delay time will be 2000 and max delay time 7000
      this.isPlaying = true;
    },
  },
};
</script>

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
