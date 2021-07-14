<template>
  <article>
    <nuxt-content :document="article" />
  </article>
</template>

<script>
export default {
    async asyncData({ $content, params}) {
        const article = await $content('gov', params.slug).fetch()

        return { article }
    }
}
</script>

<style lang="scss">
.nuxt-content {
  & h1,
  & h2,
  & h3,
  & h4,
  & h5,
  & h6 {
    & a,
    .icon-link {
      height: 14px;
      margin-top: 8px;
      position: relative;
      width: 17px;

      & .icon-link {
        color: #e1e8f5 !important;
        display: inline-block;
        background-image: url('~assets/images/link.svg');
        background-size: 14px 14px;
        visibility: hidden;
      }
    }

    &:hover {
      & .icon-link {
        visibility: visible;
      }
    }
  }

  p {
    margin-left: 1em;
  }
}
</style>