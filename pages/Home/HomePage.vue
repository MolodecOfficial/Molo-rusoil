<script setup lang="ts">

import HomeBody from "~/pages/Home/Body/HomeBody.vue";
import HomeHeader from "~/pages/Home/Body/Sections/HomeHeader.vue";
</script>

<template>
  <div class="main-container">
    <div class="video-overlay">
      <video autoplay loop muted>
        <source src="~public/overlay.mp4" type="video/mp4">
        Ваш браузер не поддерживает видео.
      </video>
      <div class="overlay"></div>
    </div>
    <HomeHeader />
    <HomeBody />
  </div>
</template>

<style scoped>
.main-container {
  position: relative;
  width: 100%;
  height: 100vh;
  overflow: hidden; /* Чтобы избежать прокрутки */
}

.video-overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100vh;
  z-index: -1; /* Убедимся, что видео позади других элементов */
}

video {
  height: auto; /* Позволяет видео адаптироваться */
  max-height: 100vh; /* Ограничение по высоте */
  min-width: 100%; /* Убирает сжатие по ширине */
  object-fit: cover; /* Сохраняет пропорции */
  width: 100%;
}

.overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: clamp(20vw, 100vw, 100vw);
  height: clamp(20%, 65vw, 56vw);
  background-color: rgba(3, 51, 157, 0.46); /* Правый фильтр */
  z-index: 1; /* Фильтр над видео */
}

@media (max-width: 1400px) {
  video {
    height: auto; /* Позволяет видео адаптироваться */
    max-height: 100vh; /* Ограничение по высоте */
    min-width: 100%; /* Убирает сжатие по ширине */
    object-fit: cover; /* Сохраняет пропорции */
  }
}

@media (max-width: 768px) {
  video {
    height: auto; /* Позволяет видео адаптироваться */
    max-height: 100vh; /* Ограничение по высоте */
    min-width: 100%; /* Убирает сжатие по ширине */
    object-fit: cover; /* Сохраняет пропорции */
  }
}
</style>