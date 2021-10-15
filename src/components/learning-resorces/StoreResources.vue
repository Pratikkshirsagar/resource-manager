<template>
  <ul v-for="resorce in resorces" :key="resorce.id">
    <learning-resource
      :title="resorce.title"
      :description="resorce.description"
      :link="resorce.link"
    ></learning-resource>
  </ul>
</template>

<script>
import LearningResource from './LearningResource.vue';

export default {
  inject: ['resorces'],
  components: {
    LearningResource,
  },
};
</script>

<style scoped>
ul {
  list-style: none;
  margin: 0;
  padding: 0;
  margin: auto;
  max-width: 40rem;
}
</style>
