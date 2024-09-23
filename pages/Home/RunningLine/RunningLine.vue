<script setup lang="ts">

import firstFrame from '~/public/Home/RunningLine/1.svg'
import secondFrame from '~/public/Home/RunningLine/2.svg'
import thirdFrame from '~/public/Home/RunningLine/3.svg'
import fourthFrame from '~/public/Home/RunningLine/4.svg'
import fiveFrame from '~/public/Home/RunningLine/5.svg'

</script>

<template>
  <section class="running-line-main">
    <div class="overlay"></div>
    <section>
      <img :src="secondFrame" alt="">
      <img :src="firstFrame" alt="">
      <img :src="fourthFrame" alt="">
      <img :src="fiveFrame" alt="">
      <img :src="thirdFrame" alt="">
    </section>
  </section>

</template>

<style scoped>
.running-line-main {
  position: relative;
  display: flex;
  justify-content: center;
  z-index: -0;
}
section {
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: clamp(20px, 5vw, 100px);
  height: clamp(40px, 13vw, 236px);
}
.overlay {
  position: absolute;
  background: linear-gradient(to right, #031946, #02143b, #123e98);
  height: clamp(40px, 13vw, 236px);
  width: 100%;
}
img {
  width: clamp(30px, 10vw, 200px);
}
</style>