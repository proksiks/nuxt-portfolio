<template>
  <div class="right-sidebar">
    <div class="right-sidebar__wrapper">
      <ul class="right-sidebar__icons socials">
        <li
          v-for="icon in fields.socials"
          :key="icon.name"
          class="right-sidebar__icon socials-icon"
        >
          <a :href="icon.link">
            <Icon :icon="icon.name" :className="icon.name" />
          </a>
        </li>
      </ul>
      <div class="right-sidebar__copiryght">© Copyright reserved</div>
    </div>
  </div>
</template>

<script>
import Icon from "~/components/Icon";
import { fields } from "~/content/componentRightSidebarSocialIcons";
export default {
  name: "rightSidebar",
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

<style>
</style>
