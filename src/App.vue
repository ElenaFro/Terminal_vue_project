<script >
import VMainWrapper from './components/v-main-wrapper.vue';
export default {
  name: 'app',
  components: {
    VMainWrapper
  }
}
</script>

<template>
  <div id="app">
    <VMainWrapper />
  </div>
</template>

<style lang="scss">
@import "node_modules/materialize-css/dist/css/materialize.min.css";
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background: white;
}
</style>
