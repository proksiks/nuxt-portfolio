<template>
  <div class="socials">
    <a
      class="social"
      :href="icon.link"
      v-for="icon in fields.socials"
      :key="icon.name"
    >
      <Icon :icon="icon.name" :className="icon.name" />
    </a>
  </div>
</template>
<script>
import Icon from "~/components/Icon";
import { fields } from "~/content/SocialIcons";
export default {
  name: "Socials",
  data() {
    return {
      fields,
    };
  },
  components: {
    Icon,
  },
};
</script>

<style lang="scss" scoped>
@import "../assets/styles/vars.scss";
.socials {
  display: flex;
  .social {
    width: 40px;
    height: 40px;
    background-color: #fff;
    border: 1px solid $color-orange;
    fill: $color-orange;
    display: flex;
    align-items: center;
    justify-content: center;
    transition: fill 0.3s ease-out, border 0.3s ease-out,
      background-color 0.3s ease-out;
    &:not(:last-child) {
      margin-right: 5px;
    }
    &:hover {
      background-color: $color-orange;
      border: 1px solid #fff;
      fill: #fff;
    }
  }
  svg {
    width: 12px;
    height: 12px;
  }
}
</style>
