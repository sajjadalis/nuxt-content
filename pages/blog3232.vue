<template>
  <div>
    <h1>Blog</h1>
  <!-- <pre>{{ posts }}</pre> -->
    <div v-for="(post, index) in posts" :key="index">
      <nuxt-content :document="post"/>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      posts: [],
      q: ''
    }
  },
  async fetch() {
    this.posts = await this.$content('blog')
    .only(['title', 'author', 'updatedAt', 'body'])
    .fetch()
  }
}
</script>
