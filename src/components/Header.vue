<template>
  <nav :class="{ 'nav-scroll': isScrolling }">
    <div class="mobile-menu">
      <div class="flex items-center justify-between w-full px-5">
        <div class="flex items-center">
          <a href="/" class="nav-logo"><img src="/img/logo.png" alt="" /></a>
        </div>
        <button @click="toggleMenu">
          <p class="text-white text-xs">menu</p>
        </button>
      </div>
    </div>
    <ul :class="{ 'nav-links': true, active: menuOpen }">
      <li><a href="/">Trang Chủ</a></li>
      <li><a href="#introduce">Giới Thiệu</a></li>
      <li><a href="#overview">Tổng Quan</a></li>
      <li><a href="#advantage">Vị Trí</a></li>
      <li><a href="#utilities">Tiện Ích</a></li>
      <li class="md:block hidden">
        <a href="/" class="nav-logo"><img src="/img/logo.png" alt="" /></a>
      </li>
      <li><a href="#langue">Thiết kế</a></li>
      <li><a href="#acreage">Mặt Bằng</a></li>
      <li><a href="#">Tiến Độ</a></li>
      <li><a href="#">Tin tức</a></li>
      <li><a href="#">Liên Hệ</a></li>
    </ul>
  </nav>
</template>

<script>
export default {
  data() {
    return {
      isScrolling: false,
      menuOpen: false,
    };
  },
  methods: {
    handleScroll() {
      this.isScrolling = window.scrollY > 50;
    },
    toggleMenu() {
      this.menuOpen = !this.menuOpen;
    },
  },
  mounted() {
    window.addEventListener("scroll", this.handleScroll);
  },
  beforeDestroy() {
    window.removeEventListener("scroll", this.handleScroll);
  },
};
</script>

<style scoped lang="scss">
nav {
  display: inline-block;
  justify-content: space-between;
  align-items: center;
  height: 80px;
  background-color: transparent;
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  transition: all 0.3s;
  z-index: 1000;
}
.nav-scroll {
  background-color: #b9a986b3;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
}
.nav-logo {
  font-size: 1.5rem;
  font-weight: bold;
}
.nav-links {
  display: none;
}
.nav-links.active {
  display: grid;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  width: 100%;
  text-align: center;
  padding: 20px 0;
  margin-top: 15px;
  background-color: var(--blue);
  li {
    padding: 10px 0;
  }
}
.nav-links a {
  text-decoration: none;
  color: var(--white);
}
.nav-links a:hover {
  color: #007bff;
}
.mobile-menu {
  display: block;
  background-color: transparent;
  border: none;
  width: 100%;
  font-size: 24px;
  cursor: pointer;
}

@media (max-width: 761px) {
  nav {
    height: 60px;
    padding: 10px 0;
  }
  .nav-logo img {
    width: 150px;
  }
}
@media (min-width: 1205px) {
  .nav-links {
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 35px;
  }
  .mobile-menu {
    display: none;
  }
}
</style>
