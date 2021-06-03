<template>
  <div class="main-navigation">
    <Header />
    <LeftSidebar />
    <RightSidebar />
    <Nuxt />
  </div>
</template>

<script>
import Header from "~/components/Header";
import LeftSidebar from "~/components/LeftSidebar";
import RightSidebar from "~/components/RightSidebar";
export default {
  name: "LeftNavigation",
  components: {
    Header,
    LeftSidebar,
    RightSidebar,
  },
};
</script>

<style>
</style>
