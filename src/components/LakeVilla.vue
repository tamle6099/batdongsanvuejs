<template>
  <div class="grid md:grid-cols-2 grid-cols-1 lake">
    <div class="flex flex-col md:px-5 md:py-10">
      <Title class="" :title="lake.title" :textname="lake.textname" />
      <Table
        :filteredItems="filteredData"
        :filteredDsc="filteredDsc"
        class="border-2"
      />
    </div>
    <div>
      <SliderThumb />
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
      lake: {
        title: "Lake Villa Park Hyatt Phu Quoc",
        textname:
          "Nằm bên một hồ nước nên thơ, cạnh những thửa ruộng bậc thang thơm dịu hương lá nếp, 10 biệt thự Lake Villa tại Park Hyatt Phu Quoc Residences đều mang tới tầm nhìn rộng mở để chiêm ngưỡng đường chân trời trên biển từ bình minh đến hoàng hôn. Không những thế, mỗi căn là một kiệt tác của nghệ thuật thiết kế nội thất với những điểm nhấn độc bản, lấy cảm hứng từ vẻ đẹp tự nhiên của Việt Nam như họa tiết cánh chuồn đỏ trên gạch men trang trí hay những món đồ gốm men Hoàng Thổ.",
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

<style lang="scss">
@media only screen and (max-width: 600px) {
  .lake {
    padding: 30px 20px;
  }
}
</style>
