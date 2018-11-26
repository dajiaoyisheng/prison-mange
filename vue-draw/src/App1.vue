<template>
  <div id="draw">
    <tools-bar></tools-bar>
    <canvas-container></canvas-container>
    <tip></tip>
    <line-size></line-size>
  </div>
</template>

<script>
  import toolsBar from './components/toolsBar';
  import canvasContainer from './components/canvasContainer';
  import lineSize from './components/lineSize';
  import tip from './components/tip';

  import init from './draw';

  export default {
    name: 'App',
    components: {
      tip,
      toolsBar,
      lineSize,
      canvasContainer
    },
    mounted() {
      init();
    }
  }
</script>

<style>
  * {
    margin: 0;
    padding: 0;
  }

  #draw {
    width: 960px;
    height: auto;
    margin: 0 auto;
  }
</style>

