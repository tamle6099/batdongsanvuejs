<template>
  <div class="hero__container">
    <div class="hero__video">
      <video class=" " autoPlay loop muted src="/video/phuquoc.mp4"></video>
    </div>
  </div>
</template>

<style lang="scss">
.hero__container {
  position: relative;
  min-height: 100vh;
  overflow: hidden;
  .hero__video {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    video {
      width: 100%;
    }
  }
}
@media only screen and (max-width: 1280px) {
  .hero__container {
    min-height: 88vh;
  }
}
@media only screen and (max-width: 900px) {
  .hero__container {
    min-height: 35vh;
  }
}
@media only screen and (max-width: 600px) {
  .hero__container {
    min-height: 0;
    height: 280px;
  }
}
@media only screen and (max-width: 450px) {
  .hero__container {
    height: 210px;
  }
}
@media only screen and (max-width: 360px) {
  .hero__container {
    height: 180px;
  }
}
</style>
