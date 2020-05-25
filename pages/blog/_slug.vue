<template>
  <div>
    <nuxt-content :document="page"/>
  </div>
</template>

<script>
export default {
  async asyncData({ $content, params, error }) {
    console.log(params);
    const slug = params.slug || "index";
    const page = await $content("posts/"+slug)
      .fetch()
      .catch(err => {
        error({ statusCode: 404, message: "Page not found" });
      });

    return {
      page
    };
  }
};
</script>
