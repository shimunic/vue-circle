<template>
  <div id="app">
    <Scene />
    <Keyboard />
  </div>
</template>

<script>
import Scene from './components/Scene.vue';
import Keyboard from './components/Keyboard.vue';

export default {
  name: 'app',
  components: {
    Scene,
    Keyboard,
  },
};
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  display: flex;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
