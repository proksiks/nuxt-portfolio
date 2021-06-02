<template>
  <div class="main-navigation">
    <Header />
    <LeftSidebar />
    <RightSidebar />
    <IndexPage />
  </div>
</template>

<script>
import Header from "~/components/Header";
import LeftSidebar from "~/components/LeftSidebar";
import RightSidebar from "~/components/RightSidebar";
import IndexPage from "~/components/pages/IndexPage";
export default {
  name: "LeftNavigation",
  components: {
    Header,
    LeftSidebar,
    RightSidebar,
    IndexPage,
  },
};
</script>

<style>
</style>
