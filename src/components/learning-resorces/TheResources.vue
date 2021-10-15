<template>
  <base-card>
    <base-button
      @click="setSelectedTab('store-resources')"
      :mode="storedResButtonMod"
      >Store Resorces</base-button
    >
    <base-button @click="setSelectedTab('add-resource')" :mode="addResButtonMod"
      >Add Resorce</base-button
    >
  </base-card>
  <keep-alive>
    <component :is="selectionTab"></component>
  </keep-alive>
</template>

<script>
import StoreResources from './StoreResources.vue';
import AddResource from './AddResource.vue';
export default {
  components: { StoreResources, AddResource },
  data() {
    return {
      selectionTab: 'store-resources',
      storedResorces: [
        {
          id: 'official-guide',
          title: 'Official Guide',
          description: 'The official vue.js documentation.',
          link: 'https://vuejs.org',
        },
        {
          id: 'google',
          title: 'Google',
          description: 'Learn to google...',
          link: 'https://google.org',
        },
      ],
    };
  },
  provide() {
    return {
      resorces: this.storedResorces,
      addResources: this.addResources,
    };
  },
  computed: {
    storedResButtonMod() {
      return this.selectionTab === 'store-resources' ? null : 'flat';
    },
    addResButtonMod() {
      return this.selectionTab === 'add-resource' ? null : 'flat';
    },
  },
  methods: {
    setSelectedTab(tab) {
      this.selectionTab = tab;
    },
    addResources(title, description, url) {
      const newResource = {
        id: new Date().toISOString(),
        title,
        description,
        link: url,
      };
      this.storedResorces.unshift(newResource);
      this.selectionTab = 'store-resources';
    },
  },
};
</script>
