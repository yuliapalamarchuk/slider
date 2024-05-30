<template>
  <div class="q-pa-md relative">
    <q-carousel
      v-model="slide"
      swipeable
      animated
      :vertical="vertical"
      :navigation="false"
      height="749px"
      class="bg-transparent text-white rounded-borders custom-carousel"
    >
      <!-- Custom navigation controls -->
      <template v-slot:control>
        <div class="custom-controls">
          <q-btn
            icon="arrow_back_ios"
            dense
            flat
            class="control-next"
            @click="goToSlide('style')"
          />
          <q-btn
            icon="arrow_forward_ios"
            dense
            flat
            class="control-next"
            @click="goToSlide('tv')"
          />
          <q-btn
            icon="arrow_forward_ios"
            dense
            flat
            class="control-next"
            @click="goToSlide('layers')"
          />
          <q-btn
            icon="arrow_forward_ios"
            dense
            flat
            class="control-next"
            @click="goToSlide('map')"
          />
        </div>
      </template>

      <q-carousel-slide
        name="style"
        class="column no-wrap flex-center custom-slide"
      >
        <h3>Кабинет Космобиологии</h3>
        <div class="q-mt-md text-center">{{ lorem }}</div>
        <img src="../assets/cosmobiology_img.png" alt="" />
      </q-carousel-slide>
      <q-carousel-slide name="tv" class="column no-wrap flex-center">
        <q-icon name="live_tv" size="56px" />
        <div class="q-mt-md text-center">{{ lorem }}</div>
      </q-carousel-slide>
      <q-carousel-slide name="layers" class="column no-wrap flex-center">
        <q-icon name="layers" size="56px" />
        <div class="q-mt-md text-center">{{ lorem }}</div>
      </q-carousel-slide>
      <q-carousel-slide name="map" class="column no-wrap flex-center">
        <q-icon name="terrain" size="56px" />
        <div class="q-mt-md text-center">{{ lorem }}</div>
      </q-carousel-slide>
    </q-carousel>
  </div>
</template>

<script>
import { ref } from "vue";

export default {
  setup() {
    const vertical = ref(true);
    const slide = ref("style");

    const goToSlide = (slideName) => {
      slide.value = slideName;
    };

    return {
      vertical,
      navigation: ref(false), // Отключаем стандартную навигацию
      slide,
      lorem:
        "Это настоящий оазис в Реянской школе. Здесь так много разнообразных растений, что можно провести не один час, любуясь их красотой.Особое восхищение вызывает «Purpura Великолепная». Растение с крупными пурпурными цветами, которые источают нежный аромат.",
      goToSlide,
    };
  },
};
</script>

<style scoped>
.relative {
  position: relative;
}

.custom-carousel-container {
  overflow: visible;
}

.custom-carousel {
  overflow: visible;
}

.custom-controls {
  position: absolute;
  left: 3rem;
  top: 50%;
  transform: translateY(-50%);
  display: flex;
  flex-direction: column;
  gap: 100px;
}
.control-next {
  background-color: #73aee6;
  padding: 25px;
}

.custom-slide {
  background-image: url("../assets/cosmology.png");
  background-repeat: no-repeat;
  background-size: contain;
  width: 1157px;
}
</style>
