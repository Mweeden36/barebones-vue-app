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
}
.hidden {
  display: none !important;
}
body {
  margin: 0;
  padding: 0;
}
html, body {
  height: 100% !important;
  font-size: 15px;
}
</style>
