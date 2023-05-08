<template>
  <header>
    <h1>ResourcesApp</h1>
  </header>
  <TheNavBar />
</template>

<script>
import TheNavBar from './components/TheNavBar.vue';

export default {
  name: 'App',
  components: {
    TheNavBar,
  },
  data() {
    return {
      resources: [],
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
header {
  width: 100%;
  background-color: #600b2c;
  color: white;
  box-shadow: rgba(0, 0, 0, 0.2) 0px 2px 7px -1px,
    rgba(0, 0, 0, 0.14) 0px 1px 1px 0px, rgba(0, 0, 0, 0.12) 0px 1px 3px 0px;
  padding: 0.5rem;
}
header h1 {
  filter: drop-shadow(2px 2px 2px black);
}
body {
  margin: 0rem;
}
</style>
