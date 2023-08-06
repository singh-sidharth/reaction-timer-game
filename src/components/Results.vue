<template>
  <h3 class="results">Reaction time: {{ score }} ms</h3>
  <p class="results">{{ rank }}</p>
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
    if (this.score < 250) this.rank = "Ninja Fingers";
    else if (this.score < 400) this.rank = "Rapid Fingers";
    else this.rank = "Snail...!";
  }
};
</script>

<style>
.results {
  border-radius: 20px;
  text-align: center;
  margin: 20px auto;
}
p.results{
  color: var(--clr-primary);
  font-size: 2rem;
}
</style>
