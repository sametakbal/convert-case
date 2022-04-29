<template>
  <HomeComponent />
</template>

<script>
import HomeComponent from "./components/HomeComponent";

export default {
  name: "App",
  components: {
    HomeComponent,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
}
body {
  background-color: #292929;
}
</style>
