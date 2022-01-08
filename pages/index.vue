<template lang="pug">
  div.main-container.is-flex.is-justify-content-center
    div.is-flex.has-text-centered.is-flex-direction-column.is-align-items-center.is-justify-content-center
      h1.ani-title.has-text-weight-bold
        span.has-text-danger Anime&nbsp;
        span.has-text-white Lorem
      p.ani-description.has-text-white Your source of random anime quotes
      div.my-6
        quote-generator
    //- ani-footer
</template>

<script>
import AniFooter from '~/components/AniFooter';
import QuoteGenerator from '~/components/QuoteGenerator';
export default {
  components: {
    AniFooter,
    QuoteGenerator,
  },
  head () {
    return {
      title: 'Anime Lorem',
      description: 'Your source of random anime quotes',
    };
  },
};
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Roboto+Mono&family=Shadows+Into+Light&display=swap');

.main-container {
  height: 100%;
}
.ani-title {
  font-family: 'Shadows Into Light', 'Verdana', 'Arial';
  font-size: 80px;
}
.ani-description {
  font-family: 'Roboto Mono', 'Verdana', 'Arial';
}
</style>
