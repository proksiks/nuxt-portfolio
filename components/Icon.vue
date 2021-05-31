<template>
  <svg-icon :name="icon" :class="className" />
</template>

<script>
export default {
  name: "Icon",
  props: {
    icon: String,
    className: String,
  },
};
</script>
