<template lang="pug">
  div.main-container.has-background-black
    nuxt
</template>

<script>
import AniFooter from '~/components/AniFooter';
export default {
  components: {
    AniFooter,
  },
};
</script>

<style scoped>
  .main-container {
    height: 100vh;
  }
</style>
