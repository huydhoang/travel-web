<template lang="">
  <!--========== SCROLL UP ==========-->
  <a href="#" class="scrollup" id="scroll-up">
    <i class="ri-arrow-up-line scrollup__icon"></i>
  </a>
</template>

<script setup>
import { onMounted } from 'vue';
onMounted(() => {
  /*==================== SHOW SCROLL UP ====================*/
  function scrollUp() {
    const scrollUp = document.getElementById('scroll-up');
    // When the scroll is higher than 200 viewport height, add the show-scroll class to the a tag with the scroll-top class
    if (this.scrollY >= 200) scrollUp.classList.add('show-scroll'); else scrollUp.classList.remove('show-scroll')
  }
  window.addEventListener('scroll', scrollUp)
})
</script>

<style scoped>
/*========== SCROLL UP ==========*/
.scrollup {
  position: fixed;
  right: 1rem;
  bottom: -20%;
  background-color: var(--first-color);
  padding: 0.5rem;
  display: flex;
  opacity: 0.9;
  z-index: var(--z-tooltip);
  transition: 0.4s;
}

.scrollup:hover {
  background-color: var(--first-color-alt);
  opacity: 1;
}

.scrollup__icon {
  color: var(--white-color);
  font-size: 1.2rem;
}

/* Show scroll */
.show-scroll {
  bottom: 5rem;
}
</style>
