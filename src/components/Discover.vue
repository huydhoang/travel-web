<template lang="">
  <!--==================== DISCOVER ====================-->
  <section class="discover section" id="discover">
    <h2 class="section__title">
      Discover the most
      <br />attractive places
    </h2>

    <div class="discover__container container swiper-container">
      <div class="swiper-wrapper">
        <!--==================== DISCOVER 1 ====================-->
        <div class="discover__card swiper-slide">
          <img src="/img/discover1.jpg" alt class="discover__img" />
          <div class="discover__data">
            <h2 class="discover__title">Bali</h2>
            <span class="discover__description">24 tours available</span>
          </div>
        </div>

        <!--==================== DISCOVER 2 ====================-->
        <div class="discover__card swiper-slide">
          <img src="/img/discover2.jpg" alt class="discover__img" />
          <div class="discover__data">
            <h2 class="discover__title">Hawaii</h2>
            <span class="discover__description">15 tours available</span>
          </div>
        </div>

        <!--==================== DISCOVER 3 ====================-->
        <div class="discover__card swiper-slide">
          <img src="/img/discover3.jpg" alt class="discover__img" />
          <div class="discover__data">
            <h2 class="discover__title">Hvar</h2>
            <span class="discover__description">18 tours available</span>
          </div>
        </div>

        <!--==================== DISCOVER 4 ====================-->
        <div class="discover__card swiper-slide">
          <img src="/img/discover4.jpg" alt class="discover__img" />
          <div class="discover__data">
            <h2 class="discover__title">Whitehaven</h2>
            <span class="discover__description">32 tours available</span>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { onMounted } from 'vue';
// bash: npm install swiper
import Swiper from 'swiper';
import 'swiper/css';
onMounted(() => {
  /*==================== SWIPER DISCOVER ====================*/
  let swiper = new Swiper(".discover__container", {
    effect: "coverflow",
    grabCursor: true,
    centeredSlides: true,
    slidesPerView: "auto",
    loop: true,
    spaceBetween: 32,
    coverflowEffect: {
      rotate: 0,
    },
  })
})
</script>

<style lang="">

</style>
