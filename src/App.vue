<template>
  <div class="container">
    <Header />
    <Tasks />
  </div>
</template>

<script>
import Header from "./components/header.vue";
import Tasks from "./components/Tasks.vue";
export default {
  name: "App",
  components: {
    Header,
    Tasks,
  },
};
</script>

<style>
#app {
  width: 100vw;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}
.container {
  width: 50vw;
  padding: 1rem;
  border: 2px black solid;
}
</style>
