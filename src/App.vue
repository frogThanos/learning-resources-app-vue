<template>
  <LearningResourceList
    :storedResources="storedResources"
  ></LearningResourceList>
</template>

<script>
import LearningResourceList from "./components/LearningResource/LearningResourceList";

export default {
  name: "App",
  components: {
    LearningResourceList,
  },
  data() {
    return {
      storedResources: [
        {
          id: "official-guide",
          title: "Official Guide",
          description: "The official Vue.js documentation.",
          link: "https://vuejs.org/",
        },
        {
          id: "google",
          title: "Google",
          description: "The official Google website.",
          link: "https://google.com/",
        },
      ],
    };
  },
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
