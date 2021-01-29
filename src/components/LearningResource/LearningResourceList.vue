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
