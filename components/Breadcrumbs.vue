<template>
  <div class="breadcrumbs">
    <div class="breadcrumbs__decorate"></div>
    <div class="breadcrumbs__wrap">
      <div class="breadcrumbs__links">
        <nuxt-link to="/" class="breadcrumbs__link breadcrumbs__link_home">HOME</nuxt-link>
        <nuxt-link :to="href" class="breadcrumbs__link breadcrumbs__link_subtitle">{{ title }}</nuxt-link>
      </div>
      <h2 class="breadcrumbs__title">{{ title }}</h2>
    </div>
    <div class="breadcrumbs__prompt">
      scroll down
    </div>
  </div>
</template>

<script>
export default {
  name: "Breadcrumbs",
  props: {
    title: {
      type: String,
      default: null,
    },
    href: String,
  },
};
</script>


<style scoped>
</style>
