<template>
  <header class="header">
    <div class="header__wrapper">
      <div class="header__logo">
        <nuxt-link to="/">
          <img src="~/assets/images/header/logo.png" alt="" />
        </nuxt-link>
      </div>
      <nav class="header__nav">
        <div class="header__burger burger">
          <div class="burger__lines">
            <span></span>
          </div>
          <div class="burger__text">
            <span>Menu</span>
          </div>
        </div>
        <ul class="header__list">
          <li><nuxt-link to="/">Home</nuxt-link></li>
          <li><nuxt-link to="/about">about</nuxt-link></li>
          <li><nuxt-link to="#">Services</nuxt-link></li>
          <li><nuxt-link to="#">portfolio</nuxt-link></li>
          <li><nuxt-link to="#">blog</nuxt-link></li>
          <li><nuxt-link to="#">contact</nuxt-link></li>
          <li>
            <div class="header__search search">
              <img src="~/assets/icons/search.svg" alt="" />
            </div>
          </li>
        </ul>
      </nav>
    </div>
  </header>
</template>

<script>
export default {
  layout: "header",
};
</script>

<style>
</style>
