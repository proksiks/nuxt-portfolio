<template>
  <div class="content-wrapper">
    <swiper ref="mySwiper" :options="swiperOptions">
      <swiper-slide :key="slide.url" v-for="slide in fields.slides">
        <img :src="require(`~/assets/images/main/${slide.url}`)" alt="" />
      </swiper-slide>
      <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
import { Swiper, SwiperSlide, directive } from "vue-awesome-swiper";
import "swiper/css/swiper.css";
import { fields } from "~/content/pageIndex";
export default {
  name: "IndexPage",
  data() {
    return {
      fields,
      swiperOptions: {
        spaceBetween: 0,
        hashNavigation: true,
        mousewheel: true,
        speed: 600,
        loop: true,
        slidesPerView: 3,
        loopAdditionalSlides: 1,
        pagination: {
          el: ".swiper-pagination",
          clickable: true,
          renderBullet: function (index, className) {
            return '<span class="' + className + '"></span>';
          },
        },
        breakpoints: {
          1440: {
            spaceBetween: -65,
          },
          0: {
            spaceBetween: -25,
          },
        },
      },
    };
  },
  components: {
    Swiper,
    SwiperSlide,
  },
  directives: {
    swiper: directive,
  },
};
</script>

