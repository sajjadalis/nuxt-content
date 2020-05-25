<template>
  <div>

      <div v-if="post.layout === 'post'">
        <nuxt-content :document="post"/>
      </div>

  </div>
</template>

<script>
export default {
  async asyncData({ $content, params, error }) {
    console.log(params);
    const slug = "posts/"+params.slug;
    const post = await $content(slug)
      .fetch()
      .catch(err => {
        error({ statusCode: 404, message: "Page not found" });
      });

      console.log(post);

    return {
      post
    };
  }
};
</script>
