<template>
  <h6>
    Reaction time: <span class="reaction-time"> {{ score }} </span> ms
  </h6>
  <p class="rankclass">{{ rank }}</p>
</template>

<script>
export default {
  props: ["score"],
  data() {
    return{
      rank: null

    }
  },
  mounted() {
    if (this.score < 250) {
      this.rank = "Ninga Fingers";
    } else if (this.score < 400) {
      this.rank = "Rapid Reflexes";
    } else {
      this.rank = "Snail Pace..";
    }
    console.log("Mounted hittedd");
  },
};
</script>

<style scoped>
.reaction-time {
  font-size: 2rem;
  color: red;
}
.rankclass {
  font-size: 1.4rem;
  color: #0faf87;
  font-weight: bold;
}
</style>
