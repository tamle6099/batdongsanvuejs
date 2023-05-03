<template>
  <div class="acreage norepet md:py-24 py-12" id="acreage">
    <div class="container text-center mx-auto">
      <h1 class="md:text-3xl text-lg text-white uppercase">
        {{ acreage.title }}
      </h1>
      <div class="grid md:grid-cols-2 grid-cols-1 gap-5 md:py-14 py-5">
        <div v-for="img in filteredAcreage">
          <img :src="img.img" alt="" />
        </div>
      </div>
      <p class="text-white max-w-4xl mx-auto md:text-base text-xs">
        {{ acreage.textname }}
      </p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      acreage: {
        title: "Mặt bằng tổng thể",

        textname:
          "Dự kiến đi vào hoạt động cuối năm 2023, dự án Park Hyatt Phu Quoc được xây dựng trên quỹ đất 65ha nhưng chỉ có duy nhất 65 căn biệt thự nghỉ dưỡng đạt chuẩn 6 sao quốc tế. Đây là 1 trong 6 khu nghỉ dưỡng mang thương hiệu Park Hyatt trên toàn thế giới, đáng để quý nhà đầu tư sành sỏi sưu tầm và sở hữu.",
      },
      images: [{ img: "/img/bds11.jpg" }, { img: "/img/bds5.jpg" }],
    };
  },
  computed: {
    filteredAcreage() {
      return this.images.filter((img) => {
        return img.img;
      });
    },
  },
};
</script>
<style lang="scss">
.acreage {
  background-image: url("/img/banner10.png");
  background-color: var(--blue);
}
@media only screen and (max-width: 600px) {
  .acreage {
    padding: 30px 20px;
  }
}
</style>
