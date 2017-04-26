<template>
  <div id="app">
    <quotes></quotes>
  </div>
</template>

<script>
import Hello from './components/Hello';
import Quotes from './components/Quotes';

export default {
  name: 'app',
  components: {
    Hello,
    Quotes,
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
