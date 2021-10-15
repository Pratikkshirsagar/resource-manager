<template>
  <the-header title="RememberMe"></the-header>
  <store-resorces :resorces="storedResorces"></store-resorces>
</template>

<script>
import StoreResorces from './components/learning-resorces/StoreResorces.vue';
import TheHeader from './components/layouts/TheHeader.vue';

export default {
  components: { StoreResorces, TheHeader },
  data() {
    return {
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
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap');

* {
  box-sizing: border-box;
}

html {
  font-family: 'Roboto', sans-serif;
}

body {
  margin: 0;
}
</style>
