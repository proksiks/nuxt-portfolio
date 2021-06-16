<template>
  <section class="container">
    <Breadcrumbs href="/about" title="About" />
    <div class="about">
      <div class="about__hero">
        <div class="about__image">
          <img src="" alt="" />
          <div class="about__text">
            Lodiz is trusted by more than 8,700 customers
          </div>
        </div>
        <div class="subtitle">About Our Company</div>
        <div class="title">
          It just might inspire you to help us build a better future
        </div>
        <div class="text">
          Lorem ipsum dolor sit amet nsectetur cing elit. Suspe ndisse suscipit
          sagittis leo sit met entum is not estibulum dignissim posuere cubilia
          durae. Leo sit met entum cubilia crae. but also the leap into
          electronic typesetting, remaining essentially unchanged. It was
          popularised in the 1960s with the release of Letraset sheets
          containing Lorem Ipsum passages and more recently.
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import Breadcrumbs from "~/components/Breadcrumbs";
export default {
  name: "about",
  components: {
    Breadcrumbs,
  },
};
</script>

<style lang="scss" scoped>
h3 {
  text-align: center;
}
</style>
