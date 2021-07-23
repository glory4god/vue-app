<template>
  <Main msg="Welcome to Your Vue.js App" />
  <Counter />
  <Gugudan />
</template>
<script>
import Main from './components/Main.vue';
import Counter from './components/Counter.vue';
import Gugudan from './components/Gugudan.vue';

export default {
  name: 'App',
  components: {
    Main,
    Counter,
    Gugudan,
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
  margin-top: 60px;
}
</style>
