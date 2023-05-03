<script>
export default {
  props: {
    filteredItems: {
      type: Array,
      default: () => [],
    },
    filteredDsc: {
      type: Array,
      default: () => [],
    },
    class: {
      type: String,
      default: "",
    },
  },
};
</script>
<template>
  <div>
    <div class="mt-8">
      <table class="bg-white table__container rounded-sm w-full" :class="class">
        <tr
          v-for="(item, index) in filteredItems"
          :key="index"
          class="text-[#4D4D56] font-medium w-full md:text-base text-sm table__bd__bottom"
        >
          <th class="table__bd__left py-3">
            {{ item.lh }}
          </th>
          <th class="table__bd__left">
            {{ item.sl }}
          </th>
          <th class="table__bd__left">
            {{ item.dt }}
          </th>
          <th>
            {{ item.sd }}
          </th>
        </tr>

        <tr
          v-for="(dsc, index) in filteredDsc"
          :key="index"
          class="table__bd__bottom table__text"
        >
          <td class="table__bd__left p-3">
            {{ dsc.lh }}
          </td>
          <td class="table__bd__left">
            {{ dsc.sl }}
          </td>
          <td class="table__bd__left">
            {{ dsc.dt }}
          </td>
          <td>
            {{ dsc.sd }}
          </td>
        </tr>
      </table>
    </div>
  </div>
  <p class="pt-5 italic text-[#808080] md:text-base text-sm">
    *Dữ liệu có thể được điều chỉnh và cập nhật theo thời gian bởi nhà phát
    triển.
  </p>
</template>

<style lang="scss">
.table__bd__left {
  border-right: 2px solid #ccc;
}

.table__bd__bottom {
  border-bottom: 2px solid #ccc;
}
.table__container {
  border-radius: 6px;
  .table__text {
    color: var(--main);
  }
  .table__text:last-child {
    border-bottom: none;
  }
}

@media only screen and (max-width: 1204px) {
  .table__container {
    .table__text {
      font-size: 12px;
      td {
        padding: 6px;
      }
    }
  }
}
</style>
