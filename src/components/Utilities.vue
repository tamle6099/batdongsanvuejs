<template>
  <div class="md:py-24 py-12 utilies norepet" id="utilities">
    <div class="utilities__title container mx-auto">
      <Title
        class="flex md:flex-row flex-col"
        :title="utilities.title"
        :textname="utilities.textname"
        :context="utilities.context"
      />
    </div>
    <div class="pt-16">
      <SliderUtilies />
    </div>
  </div>
</template>
<script setup>
import Title from "./content/Title.vue";
import SliderUtilies from "./slider/SliderUtilities.vue";
</script>
<script>
export default {
  data() {
    return {
      utilities: {
        title: "Tiện ích",
        textname:
          "Không chỉ có những dịch vụ hiếm có và trải nghiệm riêng tư dành riêng cho giới thượng lưu, thương hiệu Park Hyatt Phu Quoc còn mang đến một hành trình trải nghiệm xa xỉ mang đậm dấu ấn cá nhân, dựa trên 40 năm kinh nghiệm và kiến thức của một trong năm thương hiệu nghỉ dưỡng sang trọng nhất thế giới.",
        context:
          "Park Hyatt Phu Quoc không chỉ là một báu vật độc nhất vô nhị, mà còn là một tuyệt tác của những trải nghiệm tinh tế!",
      },
    };
  },
  components: { SliderUtilies },
};
</script>
<style lang="scss">
.utilies {
  background-image: url("/img/banner5.png");
}
.utilities__title {
  h1 {
    width: 40%;
    color: var(--black);
  }
  p {
    color: var(--black);
  }
}
@media only screen and (max-width: 600px) {
  .utilies {
    padding: 30px 20px;
  }
  .utilities__title {
    h1 {
      width: 100%;
    }
  }
}
</style>
