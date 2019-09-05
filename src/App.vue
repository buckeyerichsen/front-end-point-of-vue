<template>
  <div id="app">
    <BuckeyInput></BuckeyInput>
    <JavaVue></JavaVue>
  </div>
</template>

<script>
import BuckeyInput from "./components/Input";
import JavaVue from "./components/Java"
export default {
  name: "app",
  components: {
    BuckeyInput,
    JavaVue,
  }


};
</script>

<style>
</style>
