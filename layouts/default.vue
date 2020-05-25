<template>
  <div>
    <Header />
    <div class="spacer"></div>
    <nuxt />
  </div>
</template>
<script>
import Header from '@/layouts/header';
export default {
  components: {
    Header
  }
}
</script>
