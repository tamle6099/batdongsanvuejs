<template>
  <div class="masterfood norepet py-24">
    <div class="container mx-auto">
      <Title
        class="max-w-4xl text-center mx-auto text-white"
        :title="introduce.title"
        :textname="introduce.textname"
        :context="introduce.context"
      />
      <div class="pt-16">
        <SliderFood />
      </div>
    </div>
  </div>
</template>
<script setup>
import Title from "./content/Title.vue";
import SliderFood from "./slider/SliderFood.vue";
</script>
<script>
export default {
  data() {
    return {
      introduce: {
        title: "Master of Food & Wine",
        textname:
          "Các nhà hàng thuộc hệ thống Park Hyatt đều được phát triển bởi những siêu đầu bếp, bởi vậy đây luôn là điểm đến hàng đầu của các thực khách sành sỏi trên toàn thế giới.",
        context:
          "Master of Food & Wine là một loạt các trải nghiệm ẩm thực và đồ uống phong phú được tạo ra với niềm đam mê của người sáng lập Jay Pritzker nhằm đem lại một ẩm thực độc đáo, cùng thưởng thức nghệ thuật ẩm thực hấp dẫn và đồ uống tuyệt hảo.",
      },
    };
  },
  components: { SliderFood },
};
</script>

<style lang="scss">
.masterfood {
  background-image: url("img/banner6.png");
  background-color: var(--blue);
}
@media only screen and (max-width: 600px) {
  .masterfood {
    padding: 30px 20px;
  }
}
</style>
