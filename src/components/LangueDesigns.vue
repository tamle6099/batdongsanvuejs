<template>
  <div class="langue py-24" id="langue">
    <div class="flex container mx-auto gap-10 langue__flex">
      <div class="md:w-2/6 w-full">
        <Title
          class="langue__lh"
          :title="langue.title"
          :textname="langue.textname"
          :context="langue.context"
        />
      </div>
      <div class="grid md:grid-cols-2 grid-cols-1 w-full md:w-4/6 gap-5">
        <div v-for="context in filteredLangue" :key="context.id">
          <figure
            class="lague_hover flex items-center justify-center"
            id="rotate"
          >
            <img :src="context.image" alt="langue__img" />
            <div class="flex justify-center">
              <span class="hoverspan text-white text-center">{{
                context.text
              }}</span>
            </div>
            <div class="text">
              <p class="text-white hovertext md:text-base text-xs">
                {{ context.context }}
              </p>
            </div>
          </figure>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import Title from "./content/Title.vue";
</script>

<script>
export default {
  data() {
    return {
      langue: {
        title: "Ngôn ngữ thiết kế",
        textname:
          "Qua lăng kính của các bậc thầy kiến trúc sư quốc tế, Park Hyatt Phu Quoc Residences là tác phẩm nghệ thuật lấy cảm hứng từ chính văn hóa gia đình Việt để tạo nên một không gian sống bên biển đầy tinh tế, nơi ấm cúng khi quây quần bên gia đình và bạn bè. Mọi thứ được thể hiện rõ nét qua ngôn ngữ tinh xảo của những món đồ thủ công như sơn mài, mây tre, đồng và gốm, hòa quyện cùng kiến trúc và nghệ thuật đương đại.",
        context:
          "Mỗi căn villa nơi đây như một lời tri ân sâu sắc văn hóa truyền thống của mọi vùng miền Việt Nam.",
      },
      designs: [
        {
          context:
            "Khu nghỉ dưỡng mang âm hưởng về một ngôi làng yên bình với những ruộng bậc thang và con đường rợp bóng tre xanh. Bên trong là bộ sưu tập 65 căn biệt thự với 2-4 phòng ngủ, cao từ 1-2 tầng. Mỗi căn villa đều có cửa sổ lớn và bể bơi riêng tư, rộng rãi bên trong nhà để quý chủ nhân có thể tận hưởng trọn vẹn vẻ đẹp thiên nhiên đất trời, biển cả.",
          image: "/img/bds4.jpg",
          text: "Xúc cảm chốn bình yên",
        },
        {
          context:
            "Park Hyatt Phu Quoc Residences là dự án hiếm hoi sở hữu địa thế phân tầng tự nhiên độc đáo, bao quanh bởi ngọn đồi rợp bóng cây cùng tầm nhìn khoáng đạt chiêm ngưỡng biển khơi xanh biếc. 20 căn biệt thự mặt biển – Beach Villa sẽ được tô điểm bởi thảm thực vật phong phú bao gồm những loài hoa và cây trồng nhiệt đới nhiều màu sắc.",
          image: "/img/bds7.jpg",
          text: "Hòa hợp với thiên nhiên",
        },
        {
          context:
            "Mỗi căn biệt thự Park Hyatt Phu Quoc Residences đều lấy cảm hứng từ mối quan hệ bền chặt trong gia đình Việt, nơi nhiều thế hệ cùng chung sống trong cùng một mái nhà. Một không gian ấm cúng thân thuộc dành riêng bạn và những người thương yêu, nơi lưu giữ vô vàn những khoảnh khắc đáng nhớ bên nhau.",
          image: "/img/bds4.jpg",
          text: "Nơi an trú riêng tư",
        },
        {
          context:
            "Lấy cảm hứng từ di sản văn hóa giàu có của Việt Nam, mỗi căn villa tại Park Hyatt Phu Quoc như một bộ sưu tập thu nhỏ của những tác phẩm nghệ thuật thủ công sơn mài truyền thống, chạm khắc đồng và đan lát bằng mây tre.",
          image: "/img/bds10.jpg",
          text: "Văn hóa giao thao thiên nhiên",
        },
      ],
    };
  },
  computed: {
    filteredLangue() {
      return this.designs.filter((designs) => {
        return designs.context.toLowerCase();
      });
    },
  },
};
</script>

<style lang="scss">
.langue {
  background-image: url("/img/banner7.png");
  .langue__lh {
    p {
      line-height: 30px;
      color: var(--black);
    }
  }
}

.lague_hover {
  display: inline-block;
  position: relative;
  overflow: hidden;
  text-align: center;
  cursor: pointer;
}
.lague_hover img {
  width: 100%;
  height: 100%;
}
.lague_hover .text {
  position: absolute;
  top: 50%;
  left: 0;
  right: 0;
  padding: 10px;
  width: 100%;
  opacity: 0;
  z-index: 1;
  transition: all 0.8s ease-out;
  transition-delay: 0.2s;
}
.lague_hover:after {
  display: inline-block;
  position: absolute;
  content: "";
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: #a29061;
  opacity: 0;
  transition: all 0.8s ease-out;
}
.lague_hover:hover:after {
  opacity: 0.9;
}
.lague_hover:hover .text {
  transform: translateY(-50%);
  opacity: 1;
}
.hoverspan {
  position: absolute;
  bottom: 5%;
  margin: auto;
  -webkit-transition: 0.3s ease-in-out;
  transition: all 0.5s ease-out;
  transition-delay: 0.2s;
}
.lague_hover:hover .hoverspan {
  transform: translateY(40px);
}

@media only screen and (max-width: 1204px) {
  .langue {
    .langue__lh {
      p {
        line-height: 22px;
      }
    }
  }
}
@media only screen and (max-width: 600px) {
  .langue {
    padding: 30px 20px;
    .langue__flex {
      flex-direction: column;
    }
  }
}
</style>
