<template>
  <div class="main">
    <div class="swip">
      <swiper :thumbs="{ swiper: thumbsSwiper }" :modules="modules" class="mySwiper2">
        <swiper-slide><img src="../assets/img/activePhoto.png" /></swiper-slide
        ><swiper-slide><img src="../assets/img/Rectangle 288 gallery.png" /></swiper-slide
        ><swiper-slide><img src="../assets/img/Rectangle 289 gallery.png" /></swiper-slide
        ><swiper-slide><img src="../assets/img/Rectangle 290 gallery.png" /></swiper-slide>
        <swiper-slide><img src="../assets/img/Rectangle 291 gallery.png" /></swiper-slide>
      </swiper>
      <swiper
        @swiper="setThumbsSwiper"
        :spaceBetween="18"
        :slidesPerView="4"
        :modules="modules"
        class="mySwiper"
      >
        <swiper-slide><img src="../assets/img/Rectangle 288.png" /></swiper-slide
        ><swiper-slide><img src="../assets/img/Rectangle 289.png" /></swiper-slide
        ><swiper-slide><img src="../assets/img/Rectangle 290.png" /></swiper-slide
        ><swiper-slide><img src="../assets/img/Rectangle 291.png" /></swiper-slide>
      </swiper>
    </div>
    <div class="modification">
      <h2 class="modification__title">Modification name</h2>
      <p class="modification__description">
        Description: Are you ready to embark on the wildest bureaucratic adventure of your life, do
        you have a passion for enforcing regulations that nobody asked for: Then buckle up, because
        the Bureau of Land Mismanagement is looking for its next Ranger to join our illustrious team
        of paper-pushing eco-warriors!
      </p>
    </div>
  </div>
</template>
<script>
import { ref } from 'vue'

import { Swiper, SwiperSlide } from 'swiper/vue'

import 'swiper/css'

import 'swiper/css/thumbs'

import '../assets/styles/ModGallery/modGallery.css'

import { Thumbs } from 'swiper/modules'

export default {
  components: {
    Swiper,
    SwiperSlide
  },
  setup() {
    const thumbsSwiper = ref(null)

    const setThumbsSwiper = (swiper) => {
      thumbsSwiper.value = swiper
    }

    return {
      thumbsSwiper,
      setThumbsSwiper,
      modules: [Thumbs]
    }
  }
}
</script>
