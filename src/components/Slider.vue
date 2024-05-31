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
          <q-btn dense flat class="control-next" />
          <img src="../assets/arr_right.png" @click="goToSlide('style')" />
          <q-btn dense flat class="control-next" />
          <img src="../assets/arr_right.png" @click="goToSlide('tv')" />
          <q-btn dense flat class="control-next" />
          <img src="../assets/arr_right.png" @click="goToSlide('layers')" />
          <q-btn dense flat class="control-next" />
          <img src="../assets/arr_right.png" @click="goToSlide('map')" />
        </div>
      </template>

      <q-carousel-slide
        name="style"
        class="custom-slide-cosmology custom-slide"
      >
        <div class="custom-slide__wrapper">
          <h3 class="custom-slide__title">Кабинет Космобиологии</h3>
          <div class="q-mt-md text-left custom-slide__text">
            Это настоящий оазис в Реянской школе. Здесь так много разнообразных
            растений, что можно провести не один час, любуясь их красотой.Особое
            восхищение вызывает «Purpura Великолепная». Растение с крупными
            пурпурными цветами, которые источают нежный аромат.
          </div>
          <img src="../assets/cosmobiology_img.png" alt="" />
        </div>
      </q-carousel-slide>

      <q-carousel-slide name="tv" class="custom-slide-history custom-slide">
        <div class="custom-slide__wrapper">
          <h3 class="custom-slide__title">Кабинет Межпланетной истории</h3>
          <div class="q-mt-md text-left custom-slide__text">
            Межпланетная история — это один из самых интересных и в то же время
            сложных предметов в школе.  Амальтея настолько увлекается изучением
            межпланетной истории, что может проводить в кабинете много времени.
            После этого она с радостью делится с землянами интересными фактами,
            которые узнала.
          </div>
          <img src="../assets/history_img.png" alt="" />
        </div>
      </q-carousel-slide>

      <q-carousel-slide
        name="layers"
        class="custom-slide-astronomy custom-slide"
      >
        <div class="custom-slide__wrapper">
          <h3 class="custom-slide__title">Кабинет Астрономии</h3>
          <div class="q-mt-md text-left custom-slide__text">
            Кабинет астрономии — это место, где проходят уроки по изучению
            различных планет, звёзд и созвездий. Это любимый предмет Квази, он
            часто засматривается на фотографию звезды Sirius, висящую на стене
            возле его парты, размышляя о её характеристиках и особенностях.
          </div>
          <img src="../assets/astronomy_img.png" alt="" />
        </div>
      </q-carousel-slide>

      <q-carousel-slide name="map" class="custom-slide-class custom-slide">
        <div class="custom-slide__wrapper">
          <h3 class="custom-slide__title">Учебный класс</h3>
          <div class="q-mt-md text-left custom-slide__text">
            Это кабинет, где проходят все остальные уроки. Здесь ученики изучают
            различные предметы, которые не связаны с космосом. Главная
            особенность учебного класса — это «ГалактикаТех». «ГалактикаТех»
            включает в себя различные устройства и инструменты, которые помогают
            ученикам получать новые знания и навыки.
          </div>
          <img src="../assets/class_img.png" alt="" />
        </div>
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
      navigation: ref(false),
      slide,
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

.custom-controls img {
  cursor: pointer;
}

.custom-carousel {
  overflow: visible;
}

.custom-slide__title {
  font-family: "BrokenLed";
  font-size: 44px;
  font-weight: 400;
  line-height: 48.4px;
  text-align: left;
  margin: 0;
  padding-top: 50px;
}

.custom-slide__text {
  font-family: "Geologica";
  font-size: 24px;
  font-weight: 400;
  line-height: 32px;
  padding-top: 24px;
  padding-bottom: 40px;
}

.custom-slide__wrapper {
  max-width: 700px;
  margin: 0 auto;
}

.custom-controls {
  position: absolute;
  left: 4rem;
  top: 44%;
  transform: translateY(-50%);
  display: flex;
  flex-direction: column;
  gap: 65px;
}

.custom-slide {
  background-repeat: no-repeat;
  background-size: contain;
  max-width: 1157px;
}

.custom-slide-cosmology {
  background-image: url("../assets/cosmology.png");
}

.custom-slide-history {
  background-image: url("../assets/history.png");
}

.custom-slide-astronomy {
  background-image: url("../assets/astronomy.png");
}

.custom-slide-class {
  background-image: url("../assets/class.png");
}
</style>
