<template lang="">
  <!--==================== VIDEO TOUR ====================-->
  <section class="video section">
    <h2 class="section__title">Video Tour</h2>

    <div class="video__container container">
      <p class="video__description">
        Find out more with our video of the most beautiful and pleasant
        places for you and your family.
      </p>

      <div class="video__content">
        <video id="video-file">
          <source src="/video/video.mp4" type="video/mp4" />
        </video>

        <button class="button button--flex video__button" id="video-button">
          <i class="ri-play-line video__button-icon" id="video-icon"></i>
        </button>
      </div>
    </div>
  </section>
</template>

<script setup>
import { onMounted } from 'vue';
onMounted(() => {

  const videoFile = document.getElementById('video-file');
  const videoButton = document.getElementById('video-button');
  const videoIcon = document.getElementById('video-icon');

  function playPause() {
    if (videoFile.paused) {
      // Play video
      videoFile.play();
      // We change the icon
      videoIcon.classList.add('ri-pause-line');
      videoIcon.classList.remove('ri-play-line');
    }
    else {
      // Pause video
      videoFile.pause();
      // We change the icon
      videoIcon.classList.remove('ri-pause-line');
      videoIcon.classList.add('ri-play-line');

    }
  }
  videoButton.addEventListener('click', playPause);

  function finalVideo() {
    // Video ends, icon change
    videoIcon.classList.remove('ri-pause-line');
    videoIcon.classList.add('ri-play-line');
  }
  // ended, when the video ends
  videoFile.addEventListener('ended', finalVideo);
})

</script>

<style lang="">

</style>
