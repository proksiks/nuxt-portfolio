<template>
  <div class="left-sidebar">
    <div class="left-sidebar__wrapper">
      <div class="left-sidebar__number">
        <a href="tel:6664440000" class="number">
          <span class="left-sidebar__link-inner">666 444 0000</span>
          <span class="left-sidebar__decorate">
            <Icon icon="icon-phone" class="left-sidebar__icon icon-phone" />
          </span>
        </a>
      </div>
      <div class="left-sidebar__email">
        <a href="mailto:needhelp@lodiz.com" class="mail"
          ><span class="left-sidebar__decorate">
            <Icon
              icon="icon-email"
              class="left-sidebar__icon icon-email"
            /> </span
          ><span class="left-sidebar__link-inner">needhelp@lodiz.com</span></a
        >
      </div>
    </div>
  </div>
</template>

<script>
import Icon from "~/components/Icon";
export default {
  name: "LeftSidebar",
  components: {
    Icon,
  },
};
</script>

<style>
</style>
