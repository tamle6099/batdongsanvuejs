<script setup>
defineProps({
  title: String,
  textname: String,
  context: String,
  content: String,
  class: String,
});
</script>
<template>
  <div :class="class" class="title">
    <h1 class="text-3xl font-bold md:pb-10 pb-5 uppercase">{{ title }}</h1>
    <div class="title__text">
      <p class="text-base font-normal">{{ textname }}</p>
      <p class="text-base font-normal">{{ context }}</p>
      <p class="text-base font-normal">{{ content }}</p>
    </div>
  </div>
</template>
<style lang="scss">
@media only screen and (max-width: 1204px) {
  .title {
    h1 {
      font-size: 24px;
    }
    p {
      font-size: 12px;
    }
  }
}
@media only screen and (max-width: 600px) {
  .title {
    h1 {
      text-align: center;
      font-size: 18px;
    }
  }
}
</style>
