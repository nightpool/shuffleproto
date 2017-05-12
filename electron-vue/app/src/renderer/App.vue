<template>
  <div id="app">
    <logo></logo>
    <div id="container">
      <widget
        v-for="source in sources"
        :key="source.label"
        :source="source"
      ></widget>

      <source-controller
        v-for="source in sources"
        :key="source.label"
        :source="source"
      ></source-controller>
    </div>
    <input v-model="newSourceName" placeholder="label">
    <button v-on:click="newSource">add new data</button>
  </div>
</template>

<script>
  import Logo from 'components/Logo';
  import Widget from 'components/Widget';
  import SourceController from 'components/SourceController';

  export default {
    data: {
      sources: [
        {data: 0, label: 'Shooter Speed'},
        {data: 0, label: 'Arm Position'}
      ],
      newSourceName: ''
    },
    components: {
      Logo,
      Widget,
      SourceController
    },
    methods: {
      newSource: function () {
        let label = this.newSourceName;
        if (label) {
          this.sources.push({data: 0, label: label});
          this.newSourceName = '';
        }
      }
    }
  };
</script>

<style>
  @import url(https://fonts.googleapis.com/css?family=Lato:300);

  * {
    margin: 0;
    padding: 0;
  }

  html,
  body { height: 100%; }

  body {
    align-items: top;
    background:
      radial-gradient(
        ellipse at center,
        rgba(255, 255, 255, 1) 0%,
        rgba(229, 229, 229, .85) 100%
      );
    background-position: center;
    font-family: Lato, Helvetica, sans-serif;
    justify-content: center;
    text-align: center;
  }

  #container {
    display: flex;
  }
  button {
    padding: 4px 10px;
  }
</style>
