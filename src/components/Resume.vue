<template>
  <div class="resume">
    <h1>{{ msg }}</h1>
  </div>
</template>

<script>
export default {
  name: 'Resume',
  data() {
    return {
      msg: 'Welcome to Your Resume Component',
    };
  },
};
</script>

<style scoped>
h1 {
  font-weight: normal;
}
</style>
