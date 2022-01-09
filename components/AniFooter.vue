<template lang="pug">
  footer.footer.is-fluid.has-background-black
    div.content.has-text-centered
      a(
        href="https://github.com/MAvalleza/anime-lorem"
        target="_blank"
        rel="noopener noreferrer"
      )
        b-icon(
          icon="github"
          size="is-medium"
          type="is-white"
        )
      p.has-text-white.mt-5 Powered by&nbsp;
        a(
          href="https://animechan.vercel.app/"
          target="_blank"
          rel="noopener noreferrer"
        ).has-text-success.has-text-weight-bold Animechan
</template>

<style scoped>
.ani-footer {
  position: absolute;
  bottom: 0;
  width: 100vw;
}
</style>
