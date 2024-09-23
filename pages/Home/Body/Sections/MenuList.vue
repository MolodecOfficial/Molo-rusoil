<script setup lang="ts">
import { ref } from 'vue';

import forIncoming from 'public/Home/Body/MenuList/Incoming.png';
import forStudents from 'public/Home/Body/MenuList/Student.png';
import forScience from 'public/Home/Body/MenuList/Science.png';
import forUniversity from 'public/Home/Body/MenuList/University.png';
import forBusiness from 'public/Home/Body/MenuList/Business.png';
import forPressRoom from 'public/Home/Body/MenuList/PressRoom.png';


const icons = ref([ /* Массив с вкладками */
  {
    icon: forIncoming,
    header: { text: 'Поступающим' },
    links: [
      { text: 'Приемная комиссия\n', href: '#' },
      { text: 'Бакалавриат и специалитет', href: '#' },
      { text: 'Аспирантура', href: '#' },
      { text: 'Магистратура', href: '#' },
      { text: 'СПО (Колледж)', href: '#' },
    ]
  },
  {
    icon: forStudents,
    header: { text: 'Обучающимся' },
    links: [
      { text: 'Расписание', href: '#' },
      { text: 'Личный кабинет', href: '#' },
      { text: 'Факультеты, институты и кафедры', href: '#' },
      { text: 'Документы УГНТУ',href: '#' },
      { text: 'Обходной лист', href: '#' },
      { text: 'Институт дополнительного профессионального образования', href: '#' },
      { text: 'Стипендиальное обеспечение', href: '#' },
      { text: 'Научно-исследовательская работа студентов', href: '#' },
      { text: 'Цифровые кафедры',href: '#' }
    ]
  },
  {
    icon: forScience,
    header: { text: 'Наука и исследования' },
    links: [
      { text: 'Научные исследования', href: '#' },
      { text: 'Орган по валидации и верификации парниковых газов УГНТУ\n', href: '#' },
      { text: 'Основные научные направления', href: '#' },
      { text: 'Научные конкурсы и гранты', href: '#' },
      { text: 'Конференции и симпозиумы', href: '#' },
      { text: 'Государственное задание в сфере научной деятельности', href: '#' },
      { text: 'Научные центры и лаборатории УГНТУ', href: '#' },
      { text: 'Отдел по работе с диссертационными советами', href: '#' }
    ]
  },
  {
    icon: forBusiness,
    header: { text: 'Бизнесу' },
    links: [
      { text: 'Производственная практика', href: '#' },
      { text: 'Трудоустройство выпускников', href: '#' },
      { text: 'Институт дополнительного профессионального образования', href: '#' },
      { text: 'Проекты', href: '#' },
    ]
  },
  {
    icon: forUniversity,
    header: { text: 'Об университете' },
    links: [
      { text: 'Страница ректора', href: '#' },
      { text: 'Фонд целевого капитала УГНТУ (эндаумент-фонд)',href: '#' },
      { text: 'Документы УГНТУ', href: '#' },
      { text: 'Факультеты, институты, школы', href: '#' },
      { text: 'Образование', href: '#' },
      { text: 'Программы обучения', href: '#' },
      { text: 'Руководство университета', href: '#' },
      { text: 'Управление университетом', href: '#' }
    ]
  },
  {
    icon: forPressRoom,
    header: { text: 'Пресс-Рум' },
    links: [
      { text: 'Мероприятия', href: '#' },
      { text: 'Новости', href: '#' },
      { text: 'Объявления', href: '#' },
      { text: 'СМИ о нас', href: '#' },
      { text: 'Газета «За нефтяные кадры»', href: '#' },
    ]
  },
]);

onMounted(() => {
  activeIndex.value = null;
})

const activeIndex = ref<number | null>(null);

const showLinks = (index: number) => { /* Отобразить список */
  activeIndex.value = index;
};

function hideLinks() {
  activeIndex.value = null;
}

</script>

<template>
  <section class="easy-list">
    <div class="easy-list_overlay">
      <div class="easy-list_overlay_test"></div>
    </div>
    <section id="tttt" class="easy-list_container">
      <a href="">Поступающим</a>
      <a href="">Обучающимся</a>
      <a href="">Выпускники УГНТУ</a>
      <a href="">Наука и инновации</a>
      <a href="">Бизнесу</a>
      <a href="">Университет</a>
      <a href="">Приоритет 2030</a>
      <a href="">Вакансии УГНТУ</a>
    </section>
  </section>
  <section class="nav-links-container">
    <section
        v-for="(icon, index) in icons"
        :key="index"
        class="nav-links"
        @mouseleave="hideLinks"
    >
      <div
          @mouseenter="showLinks(index)"
          class="nav-links_container-icon"
      >
        <a class="nav-links_main" :aria-expanded="activeIndex === index">
          <img v-show="typeof icon.icon === 'string'" :src="icon.icon" alt="Icon" />
        </a>
        <div
            v-show="activeIndex === index"
            class="nav-links_dropdown"
        >
          <p>{{ icon.header.text }}</p>
          <a
              v-for="(link, linkIndex) in icon.links"
              :key="linkIndex"
              :href="link.href"
          >
            {{ link.text }}
          </a>
        </div>
      </div>
    </section>
  </section>

</template>

<style scoped>

.easy-list {
  position: absolute;
  filter: blur(10);
  height: 100%;
  width: 75vh;
  top: 0;
  left: 0;
  z-index: 0;
}
.easy-list_overlay {
  position: absolute;
  height: clamp(15%, 56vw, 100vh);
  width: clamp(20%, 65vw, 31vw);
  background-color: rgba(47, 53, 89, 0.84); /* Левый фильтр */
  opacity: 1;

}
.easy-list_overlay_test {
  position: absolute;
  filter: blur(10px);
  height: clamp(15%, 56vw, 100vh);
  width: clamp(20%, 65vw, 31vw);
  background-color: rgba(6, 13, 51, 0.68); /* Левый фильтр */
}
.easy-list_container {
  display: flex;
  align-items: start;
  top: 0;
  left: 0;
  transform: translate(100%, 10%);
  gap: 5px;
  width: clamp(170px, 10vw, 200px);
  flex-direction: column;
}
.easy-list_container a {
  font-size: clamp(6px, 1vw, 20px);
  color: #ffffff;
  transition: 0.2s transform ease-in-out, text-decoration-thickness 0.3s ease;
  text-decoration: none;
  &:hover {
    text-decoration: underline 1px;
    text-underline-offset: 4px;
    cursor: pointer;
  }
}

.nav-links-container {
  width: 10%;
  z-index: 1;
  position: relative;
}

.nav-links_container-icon {
  display: flex;
  justify-content: center;
  align-items: center;
}
.nav-links_container-icon:hover {
  cursor: pointer;
}
.nav-links {
  position: relative;
  display: flex; /* Изменено на flex для правильного отображения */
  flex-direction: column; /* Вертикальное направление */
  align-items: start; /* Центрирование по горизонтали */
  margin: clamp(3px, 1vw, 20px) 60px;
  z-index: 0;
  width: 6vh;

}

.nav-links_main {
  display: flex;
  align-items: center;
  justify-content: center;
  text-decoration: none;
  color: #333; /* Цвет текста */
  transition: color 0.3s ease;
}

.nav-links_main:hover {
  color: #007bff; /* Цвет при наведении */
}

.nav-links_dropdown {
  position: absolute;
  bottom: 100%; /* Прикрепляем к нижней части */
  left: 100%; /* Прикрепляем к правой части */
  transform: translateY(100%); /* Сдвигаем вниз, чтобы он не перекрывал иконку */
  background-color: #e3e3e3; /* Цвет фона выпадающего списка */
  border: 1px solid #ddd; /* Граница выпадающего списка */
  border-radius: 4px; /* Закругление углов */
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1); /* Тень */
  z-index: 1000; /* Чтобы выпадающий список был поверх других элементов */
  padding: 10px;
  width: 50vh;

}

.nav-links_dropdown a {
  display: flex; /* Каждая ссылка занимает всю ширину */
  padding: 8px 12px; /* Отступы для ссылок */
  text-decoration: none; /* Убрать подчеркивание */
  color: #333; /* Цвет текста ссылок */
  transition: background-color 0.3s ease; /* Плавный переход фона */
}

.nav-links_dropdown a:hover {
  background-color: #f1f1f1; /* Цвет фона при наведении на ссылку */
}

img {
  width: clamp(10px, 2vw, 40px);
  height: clamp(10px, 2vw, 40px);
  margin-bottom: 8px; /* Отступ между иконкой и текстом (вертикально) */
  transition: 0.1s all ease-in-out;
  border: 1px solid rgba(225, 225, 225, 0.26);
  border-radius: 10px;
  padding: 5px;
  &:hover {
    scale: 0.83;
    border: 1px solid rgba(255, 255, 255, 0.69);
  }
  &:active {
    border: 1px solid rgb(255, 0, 0);
  }
}
p {
  display: flex;
  justify-content: center;
  text-decoration: underline 1px;
  text-underline-offset: 4px;
  font-weight: bold;
}

</style>