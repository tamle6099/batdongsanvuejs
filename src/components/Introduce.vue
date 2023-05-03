<template>
  <div class="introduce__banner norepet" id="introduce">
    <div
      class="container mx-auto grid md:grid-cols-3 grid-cols-1 py-5 introduce__mobile"
    >
      <h3 class="text-white text-2xl flex items-center">
        {{ banner.title }}
      </h3>
      <div class="flex items-center justify-center">
        <img :src="banner.logo" :alt="banner.title" />
      </div>
      <div
        class="flex items-center md:justify-end justify-center md:gap-10 gap-5"
      >
        <h3 class="text-white text-base pr-10">{{ banner.text }}</h3>
        <div>
          <img :src="banner.bimland" :alt="banner.text" />
        </div>
      </div>
    </div>
  </div>
  <div class="introduce">
    <div class="container mx-auto md:py-24 py-12">
      <Title
        class="max-w-4xl text-center mx-auto"
        :title="introduce.title"
        :textname="introduce.textname"
        :context="introduce.context"
        :content="introduce.content"
      />

      <SliderIntro />
    </div>
  </div>
</template>
<script setup>
import Title from "./content/Title.vue";
import SliderIntro from "./slider/SliderIntro.vue";
</script>
<script>
export default {
  data() {
    return {
      banner: {
        title: "Tuyệt tác của riêng bạn",
        logo: "/img/logo.png",
        text: "Một dự án của",
        bimland: "/img/bimland.png",
      },
      introduce: {
        title: "Giới thiệu",
        textname:
          "Chào mừng bạn đã trở về nhà! Về với những cảm xúc thân thuộc của những ngôi nhà truyền thống Việt xưa. Nơi hợp nhất dòng chảy của hiện đaị với nghệ thuật thủ công truyền thống được chế tác độc bản qua ngôn ngữ của chất liệu, hoa văn và màu sắc…",
        context:
          "Nơi sở hữu địa thế riêng tư, hiếm có cùng cảnh sắc thiên nhiên thoáng đãng được lưu giữ ở thể nguyên sơ nhất",
        content:
          "Tất cả đều hội tụ bên trong tổ hợp nghỉ dưỡng mang tên Park Hyatt Phu Quoc Residences.",
      },
    };
  },
};
</script>
<style lang="scss">
.introduce__banner {
  background-image: url(/img/banner1.png);
}
.introduce {
  background-image: url("/img/banner2.png");
  background-size: cover;
  background-repeat: no-repeat;
  background-color: var(--yellowrod);
}

@media only screen and (max-width: 600px) {
  .introduce {
    padding: 20px;
  }
  .introduce__mobile {
    padding: 10px;
    h3 {
      justify-content: center;
      font-size: 18px;
      padding: 15px 0;
    }
  }
}
</style>
