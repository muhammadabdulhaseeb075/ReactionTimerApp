<template>
  <h1>Ninja Reaction Timer</h1>
  <button @click="startgame" :disabled="isPlaying">Play</button>
  <!-- Only Show block only if we are playing that's why we used v-if-->
  <!-- Binding some data into this because we want to pass in this property v-bind: or only : -->
  <!-- @end [a custom event from Block.vue to the App.vue] -->
  <Block  v-if="isPlaying" v-bind:delay="delay" @end="endGame"/> 
  <!-- <p v-if="showResults">Reaction Time: {{score}} ms</p> -->
  <Results v-if="showResults" :score="score" /> <!-- :score are props here with data binding because I want to pass score variable in data method -->
</template>

<!-- Challenges -->
<!-- 1- When the game ends, show the results component -->
<!-- 2- Output the score inside  the results component -->

<script>
// Component imports
import Block from "@/components/Block.vue";
import Results from "@/components/Results.vue";


export default {
  name: "App",
  components: {
    Block,
    Results
},
  data() {
    return {
      isPlaying: false, // must be true to start the game
      delay: null, // must be in 20 sec
      score: null,
      showResults: false
    };
  },
  methods: {
    startgame() {
      this.delay = 2000 + Math.random() * 5000; // Min delay time will be 2000 and max delay time 7000
      this.isPlaying = true;
      this.showResults = false;
    },
    endGame(reactionTime){ //We get automatically get access to the data[the second argument] that we passed in as a parameter inside the function
      this.score = reactionTime;
      this.isPlaying = false   
      this.showResults= true   
    }
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
  cursor: not-allowed
}
</style>
