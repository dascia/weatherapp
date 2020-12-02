<template>
  <WeatherComponent></WeatherComponent>
</template>

<script lang="ts">
import WeatherComponent from './components/WeatherComponent.vue';

export default {
  name: 'App',
  components: {
    WeatherComponent,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  display: flex;
  flex-direction: column;
  height: 100%;
  align-items: center;
  justify-content: center;
}
</style>
