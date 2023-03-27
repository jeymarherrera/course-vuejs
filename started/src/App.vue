<template>
  <h1>Mi primer componente en Vue JS</h1>
  <hr>
  <CarOptions></CarOptions>
  <hr>
  <CarComposition></CarComposition>
</template>

<script>
import CarComposition from "./components/CarComposition.vue";
import CarOptions from "./components/CarOptions.vue";
export default {
  components: {
    CarComposition,
    CarOptions,
  },
};
</script>

<style>
</style>