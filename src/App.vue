<template>
  <ul>
    <LearningResourceItem
    v-for="res in storedResources"
    :key="res.id"
    :title="res.title"
    :description="res.description"
    :link="res.link"
    ></LearningResourceItem>
  </ul>
</template>

<script>
import LearningResourceItem from './components/LearningResource/LearningResourceItem';

export default {
  name: 'App',
  components: {
    LearningResourceItem
  },
  data() {
    return {
      storedResources: [{
        id: 'official-guide',
        title: 'Official Guide',
        description: 'The official Vue.js documentation.',
        link: 'https://vuejs.org/',
      },
      {
        id: 'google',
        title: 'Google',
        description: 'The official Google website.',
        link: 'https://google.com/',
      }]
    }
  }
}
</script>

<style>
* {
  box-sizing: border-box;
}
body {
  margin: 0;
}
</style>
