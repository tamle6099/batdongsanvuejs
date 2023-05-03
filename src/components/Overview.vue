<template>
  <div
    class="overview grid md:grid-cols-2 grid-cols-1 gap-10 md:py-24 py-12"
    id="overview"
  >
    <div class="pl-44 overview__left">
      <h1 class="text-3xl font-bold md:pb-8 pb-4 uppercase">
        {{ overview.title }}
      </h1>
      <div v-for="context in filteredProducts" :key="context.id">
        <p class="text-base font-light overview__text">
          {{ context.name }}
        </p>
      </div>
    </div>
    <SliderThumb />
  </div>
</template>

<script setup>
import SliderThumb from "./slider/SliderThumb.vue";
</script>

<script>
export default {
  data() {
    return {
      overview: {
        title: "Tổng quan dự án",
      },
      contexts: [
        {
          name: "Tên dự án: PARK HYATT PHÚ QUỐC RESIDENCES",
        },
        {
          name: "Chủ đầu tư: Bim Land (một thành viên Tập đoàn BIM Group)",
        },

        {
          name: "Vị trí: Mặt biển Bãi Trường, thành phố Phú Quốc, tỉnh Kiên Giang",
        },
        {
          name: "Quy mô / Tổng diện tích: 65ha",
        },
        {
          name: "Loại hình sản phẩm: Duy nhất chỉ 65 căn biệt thự",
        },
        {
          name: "Phân loại sản phẩm: 20 căn Biệt thự biển (Beach Villa); 10 căn Biệt thự hồ (Lake Villa); 34 căn Biệt thự đồi (Hill Villa)",
        },
        {
          name: "Diện tích lô đất: từ 1.500m2 - 6.600m2",
        },
        {
          name: "Mật độ xây dựng: 15%",
        },
        {
          name: "Đơn vị quản lý: Park Hyatt (Tập đoàn Hyatt – Hyatt Hotels Corporation)",
        },
        {
          name: "Tư vấn kiến trúc: AR+D",
        },
        {
          name: "Tinh chỉnh chi tiết thiết kế kiến trúc: DesignLab",
        },
        {
          name: "Tư vấn cảnh quan: Intaran design",
        },
        {
          name: "Tư vấn ánh sáng: The Flaming Beacon",
        },
        {
          name: "Tư vấn triển khai ánh sáng: ASA Studios Lighting Design",
        },
        {
          name: "Tư vấn nội thất: LTW Designworks",
        },
        {
          name: "Tổng thầu thi công: CONRIC Holdings",
        },
        {
          name: "Tư vấn nội thất: LTW Designworks",
        },
        {
          name: "Quản lý dự án và giám sát chất lượng: FQM Corporation",
        },
        {
          name: "Tiến độ: đang hoàn thiện nội thất, đã có nhà mẫu",
        },
        {
          name: "Dự kiến bàn giao: năm 2023",
        },
        {
          name: "Hotline: 0903 002 554",
        },
      ],
    };
  },
  computed: {
    filteredProducts() {
      return this.contexts.filter((context) => {
        return context.name.toLowerCase();
      });
    },
  },
};
</script>
<style lang="scss">
.overview {
  background-image: url("/img/banner2.png");
}
.overview__text {
  background-image: url("/img/icontqda.svg");
  background-repeat: no-repeat;
  padding-left: 15px;
  display: grid;
  align-items: center;
  background-position-y: 8px;
  color: var(--black2);
  margin-top: 5px;
}

@media only screen and (max-width: 1280px) {
  .overview {
    .overview__left {
      padding-left: 0;
    }
    .overview__text {
      font-size: 12px;
    }
  }
}
@media only screen and (max-width: 600px) {
  .overview {
    padding: 30px 20px 30px 20px;
    .overview__left {
      h1 {
        text-align: center;
        font-size: 18px;
      }
    }
    .overview__text {
      margin-top: 0;
    }
  }
}
</style>
