<template>
  <div class="sliderintro">
    <swiper
      :rewind="true"
      :navigation="true"
      :modules="modules"
      :spaceBetween="0"
      :breakpoints="{ 600: { slidesPerView: 1 }, 900: { slidesPerView: 3 } }"
      :effect="'coverflow'"
      :coverflowEffect="{
        rotate: 50,
        stretch: 0,
        depth: 100,
        modifier: 1,
        slideShadows: true,
      }"
      class="mySwiper"
    >
      <swiper-slide><img src="/img/gt1.jpg" alt="" /> </swiper-slide>
      <swiper-slide><img src="/img/gt2.jpg" alt="" /></swiper-slide>
      <swiper-slide><img src="/img/gt3.jpg" alt="" /></swiper-slide>
      <swiper-slide><img src="/img/bds4.jpg" alt="" /></swiper-slide>
      <swiper-slide><img src="/img/bds5.jpg" alt="" /></swiper-slide>
      <swiper-slide><img src="/img/bds6.jpg" alt="" /></swiper-slide>
      <swiper-slide><img src="/img/bds7.jpg" alt="" /></swiper-slide>
      <swiper-slide><img src="/img/bds8.jpg" alt="" /></swiper-slide>
      <swiper-slide><img src="/img/bds9.jpg" alt="" /></swiper-slide>
    </swiper>
  </div>
</template>
<script>
import { Swiper, SwiperSlide } from "swiper/vue";
import "swiper/css";
import "swiper/css/effect-coverflow";

import { Navigation, EffectCoverflow } from "swiper";

export default {
  components: {
    Swiper,
    SwiperSlide,
  },
  setup() {
    return {
      modules: [Navigation, EffectCoverflow],
    };
  },
};
</script>
<style lang="scss">
.sliderintro {
  .swiper {
    width: 100%;
    padding-top: 80px;
    padding-bottom: 120px;
  }

  .swiper-slide {
    background-position: center;
    background-size: cover;
  }

  .swiper-slide img {
    display: block;
    width: 600px;
    height: 400px;
  }
  .swiper-button-prev {
    position: absolute;
    top: 90%;
    left: 44%;
    width: 50px;
    height: 50px;
    background-image: url("/img/Arow-left.svg");
    border-radius: 50%;
  }
  .swiper-button-next {
    position: absolute;
    top: 90%;
    right: 44%;
    width: 50px;
    height: 50px;
    background-image: url("/img/Arow-right.svg");
    border-radius: 50%;
  }
}
@media only screen and (max-width: 600px) {
  .sliderintro {
    .swiper {
      padding-top: 50px;
      padding-bottom: 80px;
    }
    .swiper-slide img {
      height: 280px;
    }
    .swiper-button-next {
      top: 85%;
      right: 38%;
    }
    .swiper-button-prev {
      top: 85%;
      left: 38%;
    }
  }
}
@media only screen and (max-width: 450px) {
  .sliderintro {
    .swiper-button-next {
      right: 35%;
    }
    .swiper-button-prev {
      left: 35%;
    }
  }
}
</style>
