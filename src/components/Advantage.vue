<template>
  <div class="flex advantage norepet py-24" id="advantage">
    <div class="md:w-2/6 w-full pl-16 advantage__left order-2 md:order-none">
      <img :src="advantage.map" alt="w-full" />
    </div>
    <div class="pr-44 md:w-4/6 w-full advantage__right order-1 md:order-none">
      <Title
        class="text-white flex flex-col gap-4"
        :title="advantage.title"
        :textname="advantage.textname"
        :context="advantage.context"
        :content="advantage.content"
      />
      <div class="advantage__table grid-flow-col mt-5 bg-white rounded">
        <div
          v-for="(context, index) in filteredProducts"
          :key="index"
          class="flex md:p-4 lvt__border__bottom ltvt__border__left md:gap-3 gap-2 advantage__col"
        >
          <p class="lvtv__amount pl-5">
            <span className="ltvt__span">{{ index + 1 }}</span>
          </p>
          <p class="md:pl-5 pl-3 text-[#A29061] md:text-base text-sm">
            {{ context.name }}
          </p>
        </div>
      </div>
    </div>
    <div
      class="advantage__mobie grid-flow-col mt-5 bg-white rounded md:hidden block order-3"
    >
      <div
        v-for="(context, index) in filteredProducts"
        :key="index"
        class="flex md:p-4 lvt__border__bottom ltvt__border__left md:gap-3 gap-2 advantage__col"
      >
        <p class="lvtv__amount pl-5">
          <span className="ltvt__span">{{ index + 1 }}</span>
        </p>
        <p class="md:pl-5 pl-3 text-[#A29061] md:text-base text-sm">
          {{ context.name }}
        </p>
      </div>
    </div>
    <div></div>
  </div>
</template>
<script setup>
import Title from "./content/Title.vue";
</script>
<script>
export default {
  data() {
    return {
      advantage: {
        title: "Lợi thế vị trí",
        textname:
          "Park Hyatt Phu Quoc Residences tọa lạc vị thế vàng, địa linh mang phong thủy vượng khí. Phía trước là bãi biển riêng tư trải dài hơn 1.7km, nơi được mệnh danh là địa điểm ngắm hoàng hôn đẹp nhất Bãi Trường, Phú Quốc. Phía sau là dãy núi Rồng ôm trọn hai bên cùng dòng suối tự nhiên tuôn chảy từ thượng nguồn đỉnh núi.",
        context:
          "Điểm độc đáo của dự án Park Hyatt Phu Quoc Residences còn nằm ở chỗ không gian sống luôn được lưu giữ ở vẻ nguyên bản vốn có nhất với những gốc cây cổ thụ trăm năm tuổi, cùng cây cầu tàu nhuốm màu thời gian",
        content:
          "Với cơ sở hạ tầng phát triển đồng bộ, từ khu nghỉ dưỡng Park Hyatt Phu Quoc quý chủ nhân có thể dễ dàng tiếp cận các tiện ích ngoại khu khác như:",
        map: "/img/Map.png",
      },
      contexts: [
        {
          name: "Cách thị trấn An Thới: 5km",
        },
        {
          name: "Hệ sinh thái tập đoàn Sun Group: 5km",
        },

        {
          name: "Cáp treo Hòn Thơm: 6km",
        },
        {
          name: "Biển Bãi Khem: 6km",
        },
        {
          name: "biển Bãi Sao: 7km",
        },
        {
          name: "Công viên nước Phu Quoc Marina: 7km",
        },
        {
          name: "Hệ sinh thái tập đoàn Bim Group: 7km",
        },
        {
          name: "Cách sân bay Phú Quốc 16km",
        },
        {
          name: "Cảng tàu khách quốc tế: 20km",
        },
        {
          name: "Chợ đêm Phú Quốc: 20km",
        },
        {
          name: "Thị trấn Dương Đông: 23km",
        },
        {
          name: "Thành phố không ngủ Grand World: 40km",
        },
        {
          name: "Vườn thú bán hoang dã Vinpearl Safari: 45km",
        },
        {
          name: "Công viên Vinpearl Land: 46km",
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
.advantage {
  background-image: url("/img/banner4.png");
}
.advantage__table {
  display: grid;
  grid-template-rows: repeat(7, minmax(0, 1fr));
  :nth-child(7) {
    border-bottom: none;
  }
  :nth-child(8),
  :nth-child(9),
  :nth-child(10),
  :nth-child(11),
  :nth-child(12),
  :nth-child(13),
  :nth-child(14) {
    border-right: none;
  }
  :nth-child(14) {
    border-bottom: none;
  }
}
.ltvt__border__left {
  border-bottom: 2px solid #ccc;
  border-right: 2px solid #ccc;
}

.lvt__border__bottom {
  border-bottom: 2px solid #ccc;
}

.lvtv__amount {
  color: #a29061;
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
}
.ltvt__span {
  position: absolute;
  width: 35px;
  height: 35px;
  border-radius: 50%;
  display: flex;
  border: 1px solid #a29061;
  align-items: center;
  justify-content: center;
}
.ltvt__grid {
  display: -webkit-inline-box;
  grid-template-rows: repeat(7, minmax(0, 1fr)) !important;
}

@media only screen and (max-width: 1280px) {
  .advantage {
    padding-left: 20px;
    padding-right: 20px;
    .advantage__right {
      padding-right: 0;
    }
    .advantage__left {
      padding-left: 0;
    }
    .advantage__col {
      padding: 14px;
      p {
        font-size: 14px;
      }
    }
  }
}
@media only screen and (max-width: 1204px) {
  .advantage {
    .title__text {
      p {
        font-size: 12px;
      }
    }
    .advantage__col {
      padding: 7px;
      p {
        font-size: 12px;
      }
      .ltvt__span {
        width: 26px;
        height: 26px;
      }
    }
  }
}
@media only screen and (max-width: 600px) {
  .advantage {
    padding: 30px 20px 30px 20px;
    flex-direction: column;
    gap: 10px;
    .advantage__table {
      display: none;
    }
    .advantage__mobie {
      :last-child {
        border-bottom: none;
      }
    }
    .ltvt__border__left {
      border-right: none;
    }
    .lvt__border__bottom {
      border-bottom: 1px solid #ccc;
    }
    .advantage__col {
      .ltvt__span {
        width: 20px;
        height: 20px;
      }
    }
  }
}
</style>
