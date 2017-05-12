<template>
    <div class="progress-bar" :style="{ '--bar-width': value + '%' }"></div>
</template>

<script>
  export default {
    name: 'progress-bar',
    props: ['value']
  }
</script>

<style>
  .progress-bar {
    height: 20px;
    width: 80%;
    margin: 1rem auto;
    border: 2px solid #444;
    position: relative;
  }
  .progress-bar:after {
    position: absolute;
    background-color: #444;
    display: block;
    content: '';
    height: 20px;
    width: var(--bar-width)
  }
</style>
