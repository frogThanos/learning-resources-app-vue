<template>
  <base-card>
    <base-button
      :mode="storedResButtonMode"
      @click="setSelectedTab('stored-resources')"
      >Stored Resources</base-button
    >
    <base-button
      :mode="addResButtonMode"
      @click="setSelectedTab('add-resource')"
      >Add Recource</base-button
    >
  </base-card>
  <keep-alive>
    <component :is="selectedTab"></component>
  </keep-alive>
</template>

<script>
import StoredResources from "./StoredResources";
import AddResource from "./AddResource";
export default {
  components: {
    StoredResources,
    AddResource
  },
  data() {
    return {
      selectedTab: "stored-resources",
      storedResources: [
        {
          id: "official-guide",
          title: "Official Guide",
          description: "The official Vue.js documentation.",
          link: "https://vuejs.org/"
        },
        {
          id: "google",
          title: "Google",
          description: "The official Google website.",
          link: "https://google.com/"
        }
      ]
    };
  },
  provide() {
    return {
      resources: this.storedResources,
      addResource: this.addResource,
      removeResource: this.removeResource
    };
  },
  computed: {
    storedResButtonMode() {
      return this.selectedTab === "stored-resources" ? null : "flat";
    },
    addResButtonMode() {
      return this.selectedTab === "add-resource" ? null : "flat";
    }
  },
  methods: {
    setSelectedTab(tab) {
      this.selectedTab = tab;
    },
    addResource(title, description, link) {
      const newResouce = {
        id: new Date().toISOString(),
        title,
        description,
        link
      };

      this.storedResources.unshift(newResouce);
      this.selectedTab = "stored-resources";
    },
    removeResource(id) {
      const index = this.storedResources.findIndex(res => res.id === id);
      this.storedResources.splice(index, 1);
    }
  }
};
</script>
