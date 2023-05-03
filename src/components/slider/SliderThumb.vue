<template>
  <div class="sliderthumb">
    <swiper
      :spaceBetween="10"
      :thumbs="{ swiper: thumbsSwiper }"
      class="mySwiper2"
    >
      <swiper-slide v-for="(item, index) in filteredImage" :key="index">
        <img :src="item.image"
      /></swiper-slide>
    </swiper>
    <swiper
      @swiper="setThumbsSwiper"
      :spaceBetween="10"
      :slidesPerView="4"
      :freeMode="true"
      :watchSlidesVisibility="true"
      :watchSlidesProgress="true"
      class="mySwiper"
    >
      <swiper-slide v-for="(item, index) in filteredImage" :key="index">
        <img :src="item.image"
      /></swiper-slide>
    </swiper>
  </div>
</template>
<script>
import { Swiper, SwiperSlide } from "swiper/vue";

import "swiper/css";

import "swiper/css/thumbs";
import SwiperCore, { Navigation, Thumbs } from "swiper/core";

SwiperCore.use([Navigation, Thumbs]);

export default {
  props: {
    filteredImage: {
      type: Array,
      default: () => [],
    },
  },
  components: {
    Swiper,
    SwiperSlide,
  },
  data() {
    return {
      thumbsSwiper: null,
    };
  },
  methods: {
    setThumbsSwiper(swiper) {
      this.thumbsSwiper = swiper;
    },
  },
};
</script>
<style lang="scss">
.sliderthumb {
  height: 700px;
  .swiper {
    width: 100%;
    height: 300px;
    margin-left: auto;
    margin-right: auto;
  }

  .swiper-slide {
    background-size: cover;
    background-position: center;
  }

  .mySwiper2 {
    height: 80%;
    width: 100%;
  }

  .mySwiper {
    height: 20%;
    box-sizing: border-box;
    padding: 10px 0;
  }

  .mySwiper .swiper-slide {
    width: 25%;
    height: 100%;
    opacity: 0.4;
  }

  .mySwiper .swiper-slide-thumb-active {
    opacity: 1;
  }

  .swiper-slide img {
    display: block;
    width: 100%;
    height: 100%;
    object-fit: cover;
  }
}

@media only screen and (max-width: 1204px) {
  .sliderthumb {
    height: 640px;
  }
}
@media only screen and (max-width: 600px) {
  .sliderthumb {
    height: 300px;
  }
}
</style>
