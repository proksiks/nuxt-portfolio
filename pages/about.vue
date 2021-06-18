<template>
  <section class="container">
    <Breadcrumbs href="/about" title="About" />
    <About :fields="fields" />
    <Footer />
  </section>
</template>

<script>
import Breadcrumbs from "~/components/Breadcrumbs";
import About from "~/components/pages/about/AboutPage";
import Footer from "~/components/Footer";
import { fields } from "~/content/pageAbout";

export default {
  name: "about",
  data() {
    return {
      fields,
    };
  },
  components: {
    Breadcrumbs,
    About,
    Footer,
  },
};
</script>
