<template>
  <div id="app">
    <HomePage></HomePage>
  </div>
</template>

<script>
import HomePage from "./MainView/Main.vue";
export default {
  name: 'app',
  components: {
    HomePage : HomePage
  }
};
</script>

<style>
@import url("https://maxcdn.bootstrapcdn.com/bootstrap/3.4.0/css/bootstrap.min.css");
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #0f4f8f;
  margin-top: 60px;
}
</style>
