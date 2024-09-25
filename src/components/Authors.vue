<template>
  <div>
    <a href="#authors" class="link lg:hidden">Авторы</a>
    <div class="flex gap-2">
      <h2 class="font-bold">Почта:</h2>
      <a class="link" href="mailto:lpszakri@gmail.com">lpszakri@gmail.com</a>
    </div>
    <div class="lg:flex gap-2 hidden">
      <h2 class="font-bold">Авторы:</h2>
      <span v-for="author in authors" :key="author.name">
        <a target="_blank" class="link" :href="author.link">{{
          author.name
        }}</a>
      </span>
    </div>

    <div>
      <div id="authors" class="modal">
        <div class="modal-box">
          <h1 class="text-2xl font-bold">Авторы:</h1>
          <ul class="list-disc">
            <li class="ml-4" v-for="author in authors" :key="author.name">
              <a target="_blank" class="link" :href="author.link">{{
                author.name
              }}</a>
            </li>
          </ul>
          <div class="modal-action">
            <a href="#" class="btn">Закрыть</a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      authors: [
        { name: "Гаранина Арина", link: "https://vk.com/a_sigka" },
        { name: "Ким Виктория", link: "https://vk.com/kitory_art" },
        { name: "Логинова Светлана", link: "https://vk.com/stay2211" },
        { name: "Сидорова Евгения", link: "https://vk.com/esidorova5" },
        {
          name: "Сарылов Джалсан (разработчик)",
          link: "https://vk.com/sarylov",
        },
      ],
    };
  },
};
</script>
