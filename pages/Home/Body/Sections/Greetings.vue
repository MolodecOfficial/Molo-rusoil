<script setup lang="ts">

</script>

<template>
  <section class="main_header">
    <section class="header-name">
      <h2>Ведущий</h2>
      <h2>нефтегазовый вуз</h2>
      <h2>России</h2>
    </section>
  </section>
</template>

<style scoped>
.main_header {
  position: absolute;
  top: 0;
  left: 0;
  transform: translate(77%, 25%);
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  z-index: 2;
}
h2 {
  font-size: clamp(20px, 5vw, 100px);
  font-family: "Samsung Sans", sans-serif;
  font-weight: bold;
  margin: -8px 0;
}
h2:first-child {
  color: #dedede;
}
h2:nth-child(2),
h2:nth-child(3){
  color: rgb(133, 144, 169);
}
.header-name {
  display: flex;
  flex-direction: column;
}
</style>