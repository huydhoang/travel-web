<script setup>
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup

import ScrollReveal from 'scrollreveal';

import { onMounted } from "vue";

import Header from './components/Header.vue';
import Home from './components/Home.vue';
import About from './components/About.vue';
import Discover from './components/Discover.vue';
import Experience from './components/Experience.vue';
import VideoTour from './components/VideoTour.vue';
import Places from './components/Places.vue';
import Subscribe from './components/Subscribe.vue';
import Sponsors from './components/Sponsors.vue';
import Footer from './components/Footer.vue';
import ScrollUp from './components/ScrollUp.vue';


onMounted(() => {

  /*==================== SCROLL SECTIONS ACTIVE LINK ====================*/
  const sections = document.querySelectorAll('section[id]')

  function scrollActive() {
    const scrollY = window.pageYOffset

    sections.forEach(current => {
      const sectionHeight = current.offsetHeight;
      const sectionTop = current.offsetTop - 50;
      const sectionId = current.getAttribute('id');

      if (scrollY > sectionTop && scrollY <= sectionTop + sectionHeight) {
        document.querySelector('.nav__menu a[href*=' + sectionId + ']').classList.add('active-link')
      } else {
        document.querySelector('.nav__menu a[href*=' + sectionId + ']').classList.remove('active-link')
      }
    })
  }
  window.addEventListener('scroll', scrollActive)

  /*==================== SCROLL REVEAL ANIMATION ====================*/
  const sr = ScrollReveal({
    distance: '120px',
    duration: 2800,
    // reset: true,
  })


  sr.reveal(`.home__data, .home__social-link, .home__info,
           .discover__container,
           .experience__data, .experience__overlay,
           .place__card,
           .sponsor__content,
           .footer__data, .footer__rights`, {
    origin: 'top',
    interval: 100,
  })

  sr.reveal(`.about__data,
           .video__description,
           .subscribe__description`, {
    origin: 'left',
  })

  sr.reveal(`.about__img-overlay,
           .video__content,
           .subscribe__form`, {
    origin: 'right',
    interval: 100,
  })

})


</script>

<template>
  <Header />

  <main class="main">
    <Home />
    <About />
    <Discover />
    <Experience />
    <VideoTour />
    <Places />
    <Subscribe />
    <Sponsors />
  </main>

  <Footer />

  <ScrollUp />
</template>

<style>
/* #app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
} */
@import url("https://cdn.jsdelivr.net/npm/remixicon@2.5.0/fonts/remixicon.css");

@import "./assets/css/styles.css";
</style>
