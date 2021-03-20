<template>
  <ul>
    <LearningResourceItem
      v-for="res in resources"
      :id="res.id"
      :key="res.id"
      :title="res.title"
      :description="res.description"
      :link="res.link"
    ></LearningResourceItem>
  </ul>
</template>

<script>
import LearningResourceItem from "./LearningResourceItem";
export default {
  inject: ["resources"],
  components: {
    LearningResourceItem
  }
};
</script>

<style scoped>
ul {
  list-style: none;
  margin: auto;
  padding: 0;
  max-width: 40rem;
}
</style>
