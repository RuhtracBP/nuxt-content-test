<template>
  <div>
    <article>
      <nuxt-content :document="article" />
    </article>
    <NuxtLink to="/">Home</NuxtLink>
  </div>
</template>

<script>
export default {
  async asyncData({ $content, params }) {
    console.log($content('articles', params.slug), 'AAAAAAAAAA')
    const article = await $content('articles', params.slug).fetch()

    return {
      article,
    }
  },
}
</script>

<style></style>
