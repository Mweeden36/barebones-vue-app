<template>
  <div id="app">
    <Info/>
    <Resume/>
  </div>
</template>

<script>
import Info from './components/Info';
import Resume from './components/Resume';

export default {
  name: 'App',
  components: {
    Resume,
    Info,
  },
};
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
