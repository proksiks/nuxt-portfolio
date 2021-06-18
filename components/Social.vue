<template>
  <a class="social" :href="socialLink" :class="{ orange, white }">
    <Icon :icon="socialIcon" />
  </a>
</template>
<script>
import Icon from "~/components/Icon";
export default {
  name: "Social",
  props: {
    socialLink: String,
    socialIcon: String,
    orange: Boolean,
    white: Boolean,
  },
  components: {
    Icon,
  },
};
</script>

<style lang="scss" scoped>
</style>
