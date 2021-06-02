<template>
  <header class="header">
    <div class="header__wrapper">
      <div class="header__logo">
        <nuxt-link to="/">
          <img src="~/assets/images/header/logo.png" alt="" />
        </nuxt-link>
      </div>
      <div class="header__burger burger">
        <div
          class="burger__lines"
          @click="menuShow = !menuShow"
          :class="{ _active: menuShow }"
        >
          <span></span>
        </div>
        <div
          class="burger__text"
          @click="menuShow = !menuShow"
          :class="{ _active: menuShow }"
        >
          <span>Menu</span>
        </div>
      </div>
      <nav class="header__nav" :class="{ _active: menuShow }">
        <ul class="header__list">
          <li
            v-for="link in fields.links"
            :key="link.name"
            @click="menuShow = false"
          >
            <nuxt-link :to="link.link">{{ link.name }}</nuxt-link>
          </li>
          <li>
            <div class="header__search search">
              <div class="search-box">
                <input type="text" />
                <span></span>
              </div>
            </div>
          </li>
          <li class="socials" :class="{ _active: menuShow }">
            <ul class="socials__icons">
              <li
                v-for="icon in fields.socials"
                :key="icon.name"
                class="socials__icon"
              >
                <a :href="icon.link">
                  <Icon :icon="icon.name" :className="icon.name" />
                </a>
              </li>
            </ul>
          </li>
        </ul>
      </nav>
    </div>
  </header>
</template>

<script>
import { fields } from "~/content/componentHeader";
export default {
  name: "Header",
  data() {
    return {
      fields,
      menuShow: false,
      openSearch: false,
    };
  },
};
</script>

<style lang="scss" scoped>
.socials {
  display: none;
  &._active {
    @media (max-width: 768px) {
      display: block;
    }
  }
  &__icons {
    display: flex;
    justify-content: center;
    align-items: center;
    @media (max-width: 400px) {
      flex-wrap: wrap;
    }
  }
  &__icon {
    border: 1px solid #7a7c83;
    transition: all 0.3s ease;
    margin: 30px 10px;
    @media (max-width: 400px) {
      margin: 30px;
    }
    a {
      display: flex;
      align-items: center;
      justify-content: center;
      padding: 12px;
    }
    .icon {
      width: 13px;
      height: 13px;
      fill: #7a7c83;
      transition: fill 0.3s ease-out;
      &-phone{
        padding: 0;
      }
    }

    &:hover {
      .icon {
        fill: #cc9b55;
      }
      border: 1px solid #cc9b55;
    }
  }
}
</style>
