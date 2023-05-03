<template>
  <div class="grid md:grid-cols-2 grid-cols-1 beackvilla">
    <div class="order-2 md:order-none">
      <SliderThumb />
    </div>
    <div class="flex flex-col md:px-5 md:py-10 order-1 md:order-none">
      <Title class="" :title="beack.title" :textname="beack.textname" />
      <Table :filteredItems="filteredData" :filteredDsc="filteredDsc" />
    </div>
  </div>
</template>
<script setup>
import Title from "./content/Title.vue";
import Table from "./content/Table.vue";
import SliderThumb from "./slider/SliderThumb.vue";
</script>
<script>
export default {
  data() {
    return {
      beack: {
        title: "Beach Villa Park Hyatt Phu Quoc",
        textname:
          "Bộ sưu tập 20 biệt thự Beach Villa nằm dọc theo bờ biển, với tầm nhìn ôm trọn biển ngọc mà bạn có thể chiêm ngưỡng từ phòng khách sang trọng hay từ bể bơi riêng dài 17m. Một bể bơi khác sau nhà được bao quanh bởi cây xanh đảm bảo sự thoải mái cho các thành viên. Mỗi biệt thự được trang trí bởi những viên gạch thủ công mang sắc xanh celadon, nhiều món đồ nội thất được sáng tạo riêng, tất cả tạo nên nét đặc trưng độc đáo của những biệt thự Beach Villa",
      },
      tables: [
        {
          lh: "Loại hình",
          sl: "Số lượng",
          dt: "Diện tích đất (m2)",
          sd: "Diện tích sử dụng ( m2 )",
        },
      ],
      dsc: [
        {
          lh: "1 tầng, 2 phòng ngủ",
          sl: "6",
          dt: "1.520 - 1.531",
          sd: "765",
        },
        {
          lh: "tầng, 3 phòng ngủ",
          sl: "10",
          dt: "1.826 - 2.025",
          sd: "1.018",
        },
      ],
    };
  },
  computed: {
    filteredData() {
      return this.tables.filter((context) => {
        return context.lh;
      });
    },
    filteredDsc() {
      return this.dsc.filter((item) => {
        return item.lh;
      });
    },
  },
};
</script>
