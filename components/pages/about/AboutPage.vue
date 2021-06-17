<template>
  <div class="about">
    <div class="about__hero">
      <div class="about__image">
        <img src="~assets/images/about/top-img.jpg" alt="" />
        <div class="about__text text">
          Lodiz is trusted by more than 8,700 customers
        </div>
      </div>
      <div class="about__subtitle subtitle">About Our Company</div>
      <div class="about__title title">
        It just might inspire you to help us build a better future
      </div>
      <div class="about__text text">
        Lorem ipsum dolor sit amet nsectetur cing elit. Suspe ndisse suscipit
        sagittis leo sit met entum is not estibulum dignissim posuere cubilia
        durae. Leo sit met entum cubilia crae. but also the leap into electronic
        typesetting, remaining essentially unchanged. It was popularised in the
        1960s with the release of Letraset sheets containing Lorem Ipsum
        passages and more recently.
      </div>
    </div>
    <div class="about__team">
      <div class="about__subtitle subtitle">our experts</div>
      <div class="about__title title">Meet the team</div>
      <div class="about__teams">
        <div class="about__team">
          <div class="about__team-img">
            <img src="#" alt="" />
          </div>
          <div class="about__team-name name">Kevin Hardson</div>
          <div class="about__team-position position">ceo / DESIGNER</div>
          <Socials />
        </div>
      </div>
    </div>
    <div class="about__stats">
      <div class="about__counter counter">
        <span class="counter__number">990</span>
        <span class="counter__text">happy customers</span>
      </div>
      <div class="about__counter counter">
        <span class="counter__number">16</span>
        <span class="counter__text">awards won</span>
      </div>
      <div class="about__counter counter">
        <span class="counter__number">30</span>
        <span class="counter__text">years experience</span>
      </div>
      <div class="about__counter counter">
        <span class="counter__number">247</span>
        <span class="counter__text">projects completed</span>
      </div>
    </div>
    <div class="about__slider">
      <div class="swiper-container about__slider-person">
        <div class="swiper-wrapper">
          <div class="swiper-slide">Slide 1</div>
          <div class="swiper-slide">Slide 2</div>
          <div class="swiper-slide">Slide 3</div>
        </div>
      </div>
      <div class="swiper-container about__slider-content">
        <div class="swiper-wrapper">
          <div class="swiper-slide">Slide 1</div>
          <div class="swiper-slide">Slide 2</div>
          <div class="swiper-slide">Slide 3</div>
        </div>
        <div class="swiper-pagination"></div>
      </div>
    </div>
  </div>
</template>

<script>
import Socials from "~/components/Socials";
import { Swiper, SwiperSlide, directive } from "vue-awesome-swiper";
import "swiper/css/swiper.css";
export default {
  name: "componentAbout",
  data() {
    return {
      swiperOptions: {
        spaceBetween: 0,
        hashNavigation: true,
        mousewheel: true,
        speed: 1500,
        duration: 2000,
        loop: true,
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
    Socials,
    Swiper,
    SwiperSlide,
  },
  directives: {
    swiper: directive,
  },
};
</script>

<style>
</style>
