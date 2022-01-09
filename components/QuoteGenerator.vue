<template lang="pug">
  div.container.is-centered
    b-button(
      type="is-info"
      :loading="loading"
      :disabled="disabled"
      @click="generate"
    ) GENERATE A WEEB QUOTE
</template>

<script>
export default {
  data () {
    return {
      loading: false,
    };
  },
  methods: {
    async generate () {
      try {
        this.loading = true;
        const res = await fetch('https://animechan.vercel.app/api/random');
        const data = await res.json();
        console.log('data', data);
      } catch (e) {
        console.error(e);
        this.$buefy.snackbar.open({
          message: e.message,
          type: 'is-danger',
          position: 'is-top',
        });
      } finally {
        this.loading = false;
      }
    },
  },
};
</script>
