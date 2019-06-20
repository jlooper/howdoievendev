<template>
  <div id="app">
    <Home/>
  </div>
</template>

<script>
import Home from "./components/Home.vue";

export default {
  name: "app",
  components: {
    Home
  }
};
</script>

<style>
body {
  background-color: #fffaff;
  padding: 0px;
  margin: 0px;
}
h1,
h2 {
  font-family: "Muli", sans-serif;
  color: #0a2463;
}
.headline {
  font-size: 3em;
}
#app {
  font-family: "Muli", sans-serif;
  color: #1e1b18;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  font-size: 1.5em;
}
</style>
