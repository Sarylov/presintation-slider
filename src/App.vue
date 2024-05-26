<template>
  <div class="h-screen w-full relative flex justify-end items-center p-4">
    <img
      v-for="(image, index) in images"
      :key="index"
      :src="image"
      alt="Slide"
      :class="{ active: currentSlide === index }"
      class="opacity-0 absolute left-0 top-0 object-contain w-full h-full -z-10"
    />
    <div class="z-10 flex flex-col gap-2">
      <button
        v-for="(image, index) in images"
        class="btn"
        :class="{ activeBtn: currentSlide === index }"
        @click="setCurrentSlide(index)"
      >
        {{ index + 1 }}
      </button>
    </div>
  </div>
</template>

<script>
// Импортируем изображения
import image1 from "@/assets/images/image1.png";
import image2 from "@/assets/images/image2.png";
import image3 from "@/assets/images/image3.png";
import image4 from "@/assets/images/image4.png";
import image5 from "@/assets/images/image5.png";
import image6 from "@/assets/images/image6.png";
import image7 from "@/assets/images/image7.png";
import image8 from "@/assets/images/image8.png";
import image9 from "@/assets/images/image9.png";

export default {
  data() {
    return {
      currentSlide: 1,
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
      ],
    };
  },
  methods: {
    setCurrentSlide(currentSlide) {
      this.currentSlide = currentSlide;
    },
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
