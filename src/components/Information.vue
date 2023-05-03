<template>
  <div class="information norepet py-5 md:py-24 md:pr-24">
    <div class="container mx-auto flex justify-center items-center dktt__flex">
      <div
        class="md:w-[600px] md:h-[490px] w-full h-full bg-[#0D314E] md:p-10 p-5"
      >
        <h1 class="md:text-3xl text-lg text-white font-semibold uppercase">
          Đăng ký nhận thông tin
        </h1>
        <p>front</p>
      </div>
      <div class="information__affter">
        <p class="pt-5 md:text-base text-sm">
          Mọi thông tin quý khách cung cấp sẽ được bảo mật, chỉ phục vụ mục đích
          tư vấn, giới thiệu sản phẩm
        </p>
        <p class="pt-2 md:text-base text-sm">
          Cung cấp thông tin nhanh chống và cập nhật bảng giá mới nhất từ chủ
          đầu tư
        </p>
        <p class="pt-2 md:text-base text-sm">
          Hỗ trọ khách hàng tìm căn phù hợp với ngân sách. Không thu thêm bất cứ
          khoản phí nào
        </p>
        <p class="pt-2 md:text-base text-sm">
          Hỗ trợ thủ tục trực tiếp với chủ đầu tư, trước và sau khi bán hàng
        </p>
      </div>
    </div>
  </div>
</template>
<style lang="scss">
.information {
  background-image: url("/img/banner4.png");
}
.information__affter {
  background-image: url("/img/Sen.png");
  background-repeat: no-repeat;
  background-size: cover;
  padding: 40px 30px 0 40px;
  width: 500px;
  color: white;
  font-weight: 300;
  font-style: italic;
  height: 450px;
  margin: 15px -100px;
}
@media only screen and (max-width: 600px) {
  .information {
    padding: 30px 20px;
    .dktt__flex {
      flex-direction: column;
    }
    .information__affter {
      padding: 20px;
      width: 100%;
      height: 100%;
    }
  }
}
</style>
