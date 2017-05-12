<template>
  <svg class="progress-circle" :style="{ '--perc': value }" viewBox="0 0 31.83 31.83">
    <circle r="15.915" cx="15.915" cy="15.915" />
  </svg>
</template>

<script>
  export default {
    name: 'progress-circle',
    props: ['value']
  }
</script>

<style>
  .progress-circle {
    height: 70px;
    width: 70px;
    margin: 2em auto 0.5em;
    fill: none;
    stroke: #444;
    stroke-width: 11;
    stroke-dasharray: var(--perc) 100;
    overflow: visible;
    /*transition: stroke-dasharray 1s ease;*/
    transform: rotateZ(90deg);
  }
</style>
