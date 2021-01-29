<template>
  <li>
    <BaseCard>
      <header>
        <h3>{{ title }}</h3>
        <button>Delete</button>
      </header>
      <p>{{ description }}</p>
      <nav>
        <a :href="link">View resource</a>
      </nav>
    </BaseCard>
  </li>
</template>

<script>
import BaseCard from "../UI/BaseCard";
export default {
  props: ["title", "description", "link"],
  components: {
    BaseCard,
  },
};
</script>

<style scoped>
li {
  margin: auto;
  max-width: 40rem;
}
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
</style>
