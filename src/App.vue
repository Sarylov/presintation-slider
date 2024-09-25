<template>
  <div class="h-screen w-full flex flex-col">
    <div
      class="flex flex-grow justify-end items-center p-4 flex-col lg:flex-row"
    >
      <div class="relative h-full w-full">
        <img
          v-for="(image, index) in images"
          :key="index"
          :src="image"
          alt="Slide"
          :class="{ active: currentSlide === index }"
          class="opacity-0 absolute left-0 top-0 object-contain w-full h-full -z-10"
        />
      </div>
      <div class="flex w-full lg:w-auto flex-col lg:items-end">
        <h2>Этажи:</h2>
        <div class="z-10 flex lg:flex-col gap-2 justify-between flex-wrap">
          <button
            v-for="index in 9"
            class="btn btn-sm btn-square"
            :class="{ activeBtn: currentSlide === index - 1 }"
            @click="setCurrentSlide(index - 1)"
          >
            {{ index }}
          </button>
        </div>
        <div class="divider h-1"></div>
        <button
          class="btn btn-sm md:btn"
          :class="{ activeBtn: currentSlide === 9 }"
          @click="setCurrentSlide(9)"
        >
          Условные обозначения
        </button>
      </div>
    </div>
    <div class="flex justify-between px-4 items-center">
      <Authors />
      <Feedback />
    </div>
  </div>
</template>

<script>
import Feedback from "./components/Feedback.vue";
import Authors from "./components/Authors.vue";

// Импортируем изображения
import image1 from "@/assets/images/1.png";
import image2 from "@/assets/images/2.png";
import image3 from "@/assets/images/3.png";
import image4 from "@/assets/images/4.png";
import image5 from "@/assets/images/5.png";
import image6 from "@/assets/images/6.png";
import image7 from "@/assets/images/7.png";
import image8 from "@/assets/images/8.png";
import image9 from "@/assets/images/9.png";
import image10 from "@/assets/images/10.png";

export default {
  data() {
    return {
      currentSlide: 0,
      images: [
        image1,
        image2,
        image3,
        image4,
        image5,
        image6,
        image7,
        image8,
        image9,
        image10,
      ],
    };
  },
  methods: {
    setCurrentSlide(currentSlide) {
      this.currentSlide = currentSlide;
    },
  },
  components: {
    Feedback,
  },
};
</script>

<style scoped>
.active {
  @apply opacity-100;
}

.activeBtn {
  @apply btn-primary;
}
</style>
