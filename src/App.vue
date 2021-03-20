<template>
  <the-header title="RememberMe"></the-header>
  <the-resources></the-resources>
</template>

<script>
import TheHeader from "./components/layouts/TheHeader";
import TheResources from "./components/LearningResource/TheResources";

export default {
  name: "App",
  components: {
    TheHeader,
    TheResources
  }
};
</script>

<style>
* {
  box-sizing: border-box;
}
body {
  margin: 0;
}
</style>
