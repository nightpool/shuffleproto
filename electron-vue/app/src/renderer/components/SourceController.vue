<template>
  <input class="source-controller" v-model="source.data" type="range">
</template>

<script>
  export default {
    name: 'source-controller',
    props: ['source']
  }
</script>

<style>
  .source-controller {
    margin: 5rem 2rem;
    height: 140px;
    width: 40px;
    -webkit-appearance: slider-vertical;
  }
</style>
