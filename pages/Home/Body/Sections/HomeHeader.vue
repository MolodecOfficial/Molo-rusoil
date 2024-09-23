<script setup lang="ts">

</script>

<template>
  <header>
    <a class="main-logo" href="">
      <img class="logo" src="../../../../public/Home/logo.svg" alt="">
      <img class="logo-circle" src="../../../../public/Home/logo-circle.svg" alt="">
    </a>
    <section class="main-links">
      <NuxtLink class="link" to="/">Подать документы</NuxtLink>
      <NuxtLink class="link" to="/Auth">Личный кабинет абитуриента</NuxtLink>
      <NuxtLink class="link" to="/">Списки поступающих</NuxtLink>
    </section>
  </header>

</template>

<style scoped>
header {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  padding: 10px 20px;
}
.main-logo {
  background-color: #022469;
  width: clamp(30px, 10vw, 130px);
  height: clamp(30px, 10vw, 130px);
  display: flex;
  justify-content: center;
  align-items: center;
  border-radius: 50%;
  z-index: 1;
}
.logo {
  height: clamp(10px, 5vw, 70px);
  width: clamp(10px, 5vw, 70px);
  display: flex;
  justify-content: center;
  align-items: center;
}

.logo-circle {
  position: absolute;
  z-index: 3;
  height: clamp(30px, 10vw, 120px);
  width: clamp(30px, 10vw, 120px);
  animation: spin 15s linear infinite; /* Используем 'linear' для равномерного вращения */
  display: flex;
  justify-content: center;
  align-items: center;
}

@keyframes spin {
  from {
    transform: rotate(0deg); /* Начальная позиция */
  }
  to {
    transform: rotate(-360deg); /* Конечная позиция */
  }
}


.main-links {
  display: flex;
  justify-content: center;
  align-items: start;
  flex-direction: column;
  gap: 6px;
}
.link {
  color: #eee;
  font-weight: lighter;
  font-size: clamp(10px, 1vw, 20px);
  margin: 0 15px;
  transition: 0.2s transform ease-in-out, text-decoration-thickness 0.3s ease;
  text-decoration: none;
  &:hover {
    text-decoration: underline 1px;
  }
}

</style>