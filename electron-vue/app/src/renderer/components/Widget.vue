<template>
  <div class="widget">
    <div class="widget--header">{{ source.label }}</div>
    <div class="widget--content">
      Value: <span>{{ source.data }}</span>
      <progress-bar :value="source.data"></progress-bar>
      <progress-circle :value="source.data"></progress-circle>
    </div>
  </div>
</template>

<script>
  import ProgressBar from 'components/ProgressBar'
  import ProgressCircle from 'components/ProgressCircle'

  export default {
    name: 'widget',
    props: ['source'],
    components: {
      ProgressBar,
      ProgressCircle
    }
  }
</script>

<style>
  .widget {
    width: 200px;
    margin: 1rem;
    border: 2px solid #444;
    border-radius: 7px;
  }
  .widget--header {
    padding: 1rem;
    background-color: #444;
    color: white;
    font-size: 1.3em;
  }
  .widget--content {
    padding: 1rem;
    font-weight: bold;
  }
</style>
