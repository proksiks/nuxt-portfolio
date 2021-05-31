<template>
  <header class="header">
    <div class="header__wrapper">
      <div class="header__logo">
        <nuxt-link to="/">
          <img src="~/assets/images/header/logo.png" alt="" />
        </nuxt-link>
      </div>
      <div class="header__burger burger">
        <div class="burger__lines">
          <span></span>
        </div>
        <div class="burger__text">
          <span>Menu</span>
        </div>
      </div>
      <nav class="header__nav">
        <ul class="header__list">
          <li><nuxt-link to="/">Home</nuxt-link></li>
          <li><nuxt-link to="/about">about</nuxt-link></li>
          <li><nuxt-link to="#">Services</nuxt-link></li>
          <li><nuxt-link to="#">portfolio</nuxt-link></li>
          <li><nuxt-link to="#">blog</nuxt-link></li>
          <li><nuxt-link to="#">contact</nuxt-link></li>
          <li>
            <div class="header__search search">
              <div class="search-box">
                <input type="text" />
                <span></span>
              </div>
            </div>
          </li>
        </ul>
      </nav>
    </div>
  </header>
</template>

<script>
import Icon from "~/components/Icon";
export default {
  layout: "header",
  components: {
    Icon,
  },
};
</script>

<style>
</style>
