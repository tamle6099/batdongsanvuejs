<template>
  <swiper
    :rewind="true"
    :breakpoints="{ 600: { slidesPerView: 1 }, 900: { slidesPerView: 3 } }"
    :spaceBetween="30"
    :navigation="true"
    :modules="modules"
    class="sliderfood"
  >
    <swiper-slide><img src="/img/food1.jpg" alt="" /></swiper-slide>
    <swiper-slide><img src="/img/food2.jpg" alt="" /></swiper-slide>
    <swiper-slide><img src="/img/food3.jpg" alt="" /></swiper-slide>
    <swiper-slide><img src="/img/food1.jpg" alt="" /></swiper-slide>
    <swiper-slide><img src="/img/food2.jpg" alt="" /></swiper-slide>
    <swiper-slide><img src="/img/food3.jpg" alt="" /></swiper-slide>
  </swiper>
</template>
<script>
import { Swiper, SwiperSlide } from "swiper/vue";
import "swiper/css";
import "swiper/css/scrollbar";
import { Navigation } from "swiper";
export default {
  components: {
    Swiper,
    SwiperSlide,
  },
  setup() {
    return {
      modules: [Navigation],
    };
  },
};
</script>
<style lang="scss">
.sliderfood {
  .swiper {
    width: 100%;
    height: 100%;
  }

  .swiper-slide {
    text-align: center;
    font-size: 18px;
    background: #fff;
    height: 300px;
  }

  .swiper-slide img {
    display: block;
    width: 100%;
    height: 100%;
    object-fit: cover;
  }
  .swiper-button-prev {
    position: absolute;
    bottom: 40%;
    left: 0;
    width: 50px;
    height: 50px;
    z-index: 10;
    background-image: url("/img/Arow-left.svg");
    border-radius: 50%;
  }
  .swiper-button-next {
    position: absolute;
    bottom: 40%;
    right: 0;
    width: 50px;
    height: 50px;
    z-index: 10;
    background-image: url("/img/Arow-right.svg");
    border-radius: 50%;
  }
  .swiper-button-prev:hover,
  .swiper-button-next:hover {
    opacity: 0.5;
  }
}
</style>
