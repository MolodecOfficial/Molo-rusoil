<script setup lang="ts">

import MoloNews from "~/layouts/home/UI/MoloNews.vue";



interface MoloNew {
  image: string,
  description: string,
  link: string
}

let MoloNewsArray: Array<MoloNew> = [
  {
    image: '/news/1.png',
    description: 'Заседание вузов-участников консорциума «Сетевой энергетический университет» состоялось в УГНТУ',
    link: '/in-progress'
  },
  {
    image: '/news/2.png',
    description: 'Итоги Ученого совета УГНТУ 26 сентября',
    link: '/in-progress'
  },
  {
    image: '/news/3.png',
    description: 'Вопросы промышленной робототехники обсудили в Минпромэнерго РБ',
    link: '/in-progress'
  },
  {
    image: '/news/4.png',
    description: 'Студенческий Театр «Ст. Арт» УГНТУ среди победителей!',
    link: '/in-progress'
  },
  {
    image: '/news/5.png',
    description: 'Форум «ИмпульсMedia» стартовал в Уфе',
    link: '/in-progress'
  },
  {
    image: '/news/6.png',
    description: 'Образование поколения Z обсудили в УГНТУ',
    link: '/in-progress'
  },
  {
    image: '/news/7.png',
    description: 'В слете «Наши ценности» участвовала студентка УГНТУ Ариана Акузина',
    link: '/in-progress'
  },
  {
    image: '/news/8.png',
    description: 'Победители международного экотона – команда УГНТУ «Эко будущее»!',
    link: '/in-progress'
  }
]

const showMore = ref(false);
const displayedNews = computed(() => showMore.value ? MoloNewsArray : MoloNewsArray.slice(0, 4));
</script>

<template>
  <div>
    <header>
      <p>Новости Университета</p>
    </header>
    <section>
      <div v-for="(news, idx) in displayedNews" :key="idx">
        <MoloNews
            :image="news.image"
            :description="news.description"
            :link="news.link"
        />
      </div>
      <section class="showMore">
        <button v-if="!showMore" @click="showMore = true">Показать ещё</button>
      </section>
    </section>
  </div>
</template>

<style scoped>
div {
  background-color: #e5e5e5;
  margin: 0;
  padding: 0;
}
section {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(400px, 1fr)); /* Автоматическое заполнение */
  grid-template-rows: repeat(2, 1fr); /* Позволяет строкам адаптироваться */
  grid-column-gap: 0;
  grid-row-gap: 14px;
  width: 100%; /* Занимает всю ширину */
  max-width: 100vw; /* Ограничивает максимальную ширину */
  box-sizing: border-box; /* Учитывает отступы и границы */
  justify-items: center;
}
header {
  display: flex;
  justify-content: center;
}
header p {
  font-size: 26px;
}
button {
  background-color: #5a87e7;
  color: #e3e3e3;
  border: none;
  height: 50px;
  width: 150px;
  border-radius: 50px;
  font-size: 17px;
}
.showMore {
  display: flex;
  justify-content: center;
  height: 15%;
}
</style>