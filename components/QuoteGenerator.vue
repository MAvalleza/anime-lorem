<template lang="pug">
  div.container.is-centered
    b-button(
      type="is-info"
      :loading="loading"
      @click="generate"
    ).has-text-weight-bold GENERATE A WEEB QUOTE
    b-modal(
      v-model="quoteModal"
      :width="640"
      :can-cancel="['escape', 'x']"
      trap-focus
    )
      div.card
        div.card-content
          div.content
            p.is-size-4 "{{ quoteData.quote }}"
          div.media
            div.media-content
              p.title.is-4 {{ quoteData.character }}
              p.subtitle.is-6 {{ quoteData.anime }}
        div.card-footer
          div.card-footer-item
            b-button(
              type="is-light"
              rounded
              :loading="loading"
              @click="copyToClipboard"
            ) Copy to clipboard
</template>

<script>
export default {
  data () {
    return {
      loading: false,
      quoteModal: false,
      quoteData: {},
    };
  },
  methods: {
    async generate () {
      try {
        this.loading = true;
        const res = await fetch('https://animechan.xyz/api/random');
        this.quoteData = await res.json();
        this.quoteModal = true;
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
    async copyToClipboard () {
      const { quote, character, anime } = this.quoteData;
      const text = `"${quote}" -- ${character} from ${anime}`;
      this.loading = true;
      await navigator.clipboard.writeText(text);
      this.$buefy.snackbar.open({
        message: 'Copied to clipboard',
        type: 'is-success',
        position: 'is-top',
      });
      this.loading = false;
    },
  },
};
</script>
