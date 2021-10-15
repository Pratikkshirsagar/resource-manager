<template>
  <ul v-for="resorce in resorces" :key="resorce.id">
    <learning-resorce
      :title="resorce.title"
      :description="resorce.description"
      :link="resorce.link"
    ></learning-resorce>
  </ul>
</template>

<script>
import LearningResorce from '../learning-resorces/LearningResorce.vue';

export default {
  props: ['resorces'],
  components: {
    LearningResorce,
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
