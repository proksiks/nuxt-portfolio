<template>
  <div class="content-wrapper">
    <swiper ref="mySwiper" :options="swiperOptions">
      <swiper-slide :key="slide.url" v-for="slide in fields.slides">
        <a :href="slide.link" class="slide-wrap">
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
<style lang="scss" >
.content-wrapper {
  height: 100vh;
  padding: 0 100px;
  @media (max-width: 970px) {
    padding: 0 50px 0 100px;
  }
  @media (max-width: 900px) {
    padding: 0 49px;
  }
  @media (max-width: 768px) {
    padding: 0;
  }
}
.main-footer {
  padding: 34px 0;
  background-color: #1c1e25;
  @media (max-width: 400px) {
    padding: 10px 0;
  }
  &__wrap {
    color: #fff;
    letter-spacing: 6px;
    padding: 0 90px;
    text-transform: uppercase;
    font-size: 12px;
    line-height: 1;
    font-weight: 600;
    @media (max-width: 768px) {
      padding: 0 40px;
    }
  }
  &__left {
    p {
      position: relative;
      span {
        color: #cc9b55;
      }
      &::before {
        content: "";
        position: absolute;
        left: -30px;
        top: 42%;
        transform: translateY(-50%);
        width: 20px;
        height: 1px;
        background-color: #cc9b55;
        @media (max-width: 400px) {
          display: none;
        }
      }
    }
    @media (max-width: 400px) {
      text-align: center;
    }
  }
}
.swiper-container {
  overflow: visible;
}
.swiper-counter {
  position: absolute;
  right: 60px;
  bottom: -46px;
  font-size: 12px;
  font-weight: 600;
  line-height: 1;
  color: #fff;
  @media (max-width: 1300px) {
    display: none;
  }
}

.slide-wrap {
  position: relative;
  display: block;
  overflow: hidden;
  @media (max-width: 400px) {
    margin-bottom: -1px;
  }
  &:hover {
    img {
      transform: scale(1.2);
    }
    &::before {
      background-color: rgba(0, 0, 0, 0.3);
    }
    .slide-wrap__text {
      .square {
        &::before {
          left: 10px;
        }
      }
    }
  }
  &:before {
    content: "";
    position: absolute;
    left: 0;
    top: 0;
    right: 0;
    bottom: 0;
    width: 100%;
    height: 100%;
    z-index: 2;
    transition: all 0.5s ease-out;
    background-color: rgba(0, 0, 0, 0.1);
  }
  &__link {
    position: absolute;
    left: 0;
    bottom: 0;
    width: 100%;
    z-index: 3;
    font-size: 26px;
    line-height: 1;
    transition: all 0.5s ease-out;
    font-family: "Barlow Condensed", sans-serif;
  }
  &__text {
    position: relative;
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin: 60px;
    @media (max-width: 400px) {
      margin: 20px;
      justify-content: center;
    }
    p {
      transition: color 0.5s ease-out;
    }
    &:hover {
      p {
        color: #cc9b55;
      }
    }
    .square {
      position: relative;
      width: 20px;
      height: 20px;
      border: 1px solid #cc9b55;
      &::before {
        content: "";
        position: absolute;
        top: 10px;
        left: -10px;
        width: 100%;
        height: 1px;
        background-color: #cc9b55;
        transition: all 0.5s ease-out;
      }
      @media (max-width: 800px) {
        display: none;
      }
    }
  }
}

.swiper-slide {
  img {
    display: block;
    width: 100%;
    height: calc(100vh - 80px);
    object-fit: cover;
    transition: transform 3s ease;
    @media (max-width: 400px) {
      height: calc(100vh - 30px);
    }
  }
}
.swiper-pagination-fraction,
.swiper-pagination-custom,
.swiper-container-horizontal > .swiper-pagination-bullets {
  text-align: right;
  left: auto;
  top: auto;
  right: 115px;
  bottom: -55px;
  width: auto;
  @media (max-width: 1300px) {
    right: 50px;
  }
  @media (max-width: 768px) {
    right: 20px;
  }
  @media (max-width: 400px) {
    bottom: -30px;
  }
}

.swiper-pagination-bullet {
  position: relative;
  opacity: 1;
  width: 35px;
  height: 20px;
  background: transparent;
  transition: all 0.8s ease;
  &::before {
    content: "";
    position: absolute;
    left: 0;
    top: 50%;
    transform: translateY(-50%);
    opacity: 1;
    width: 100%;
    height: 1px;
    background: #444549;
    transition: all 0.8s ease;
  }
  @media (max-width: 400px) {
    display: none;
  }
}
.swiper-pagination-bullet-active {
  &::before {
    background: #cc9b55;
  }
}
</style>

