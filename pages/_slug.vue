<template>
  <div>

    <section class="uk-section uk-section-small uk-section-default uk-padding-remove-bottom">
      <div v-if="post.layout === 'post'" class="uk-container uk-container-expand uk-margin-large-bottom content-entry">
        <h1>{{post.title}}</h1>

        <nuxt-content :document="post"/>
      </div>
    </section>

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
