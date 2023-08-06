<template>
  <h3 class="results">Reaction time: {{ score }} ms</h3>
  <p>{{ rank }}</p>
</template>

<script>
export default {
  props: ["score"],
  data() {
    return {
      rank: ""
    };
  },
  mounted() {
    if (this.score < 250) rank = "Ninja Fingers";
    else if (this.score < 400) rank = "Rapid Fingers";
    else rank = "Snail...!";
  }
};
</script>

<style>
.results {
  border-radius: 20px;
  text-align: center;
  margin: 40px auto;
}
</style>
