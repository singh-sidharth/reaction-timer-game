<template>
  <h3 class="results">
    Reaction time: {{ score }} ms
  </h3>
</template>

<script>
export default {
  props: ["score"]
}
</script>

<style>
.results {
  border-radius: 20px;
  text-align: center;
  margin: 40px auto;
}
</style>