<template>
  <div class="content-wrapper">
    <swiper ref="mySwiper" :options="swiperOptions">
      <swiper-slide :key="slide.url" v-for="slide in fields.slides">
        <a :href="slide.link" class="slide-wrap" target="_blank">
          <img :src="require(`~/assets/images/main/${slide.url}`)" alt="" />
          <div class="slide-wrap__link">
            <div class="slide-wrap__text">
              <p>{{ slide.name }}</p>
              <span class="square"></span>
            </div>
          </div>
        </a>
      </swiper-slide>
      <div class="swiper-pagination" slot="pagination"></div>
      <div class="swiper-counter" slot="pagination"></div>
    </swiper>
    <div class="main-footer">
      <div class="main-footer__wrap">
        <div class="main-footer__left">
          <p>scroll <span>&</span> swipe</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { fields } from "~/content/pageIndex";
import { Swiper, SwiperSlide, directive } from "vue-awesome-swiper";
import "swiper/css/swiper.css";
export default {
  name: "IndexPage",
  data() {
    return {
      fields,
      swiperOptions: {
        spaceBetween: 0,
        hashNavigation: true,
        mousewheel: true,
        speed: 1500,
        duration: 2000,
        loop: true,
        autoplay: {
          delay: 2000,
        },
        runCallbacksOnInit: true,
        on: {
          slideChange: function () {
            let offer = document.querySelector(".swiper-counter");
            let totalSlides = this.slides.length - 2;
            let mainIndex = this.realIndex + 1;
            offer.innerHTML = "0 " + mainIndex + " / 0 " + totalSlides / 2;
          },
        },
        pagination: {
          el: ".swiper-pagination",
          clickable: true,
        },
        breakpoints: {
          320: {
            slidesPerView: 1,
            spaceBetween: 0,
          },
          800: {
            slidesPerView: 2,
          },
          1300: {
            slidesPerView: 3,
            spaceBetween: -1,
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
<style lang="scss">

</style>

