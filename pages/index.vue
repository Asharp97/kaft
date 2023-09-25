<template>
  <div>
    <navbar class="navbar container">
      <Icon name="solar:list-outline" class="icon" @click="this.menu = !this.menu" v-if="!this.menu" />
      <Icon name="solar:close-square-broken" class="icon closeIcon" @click="this.menu = !this.menu" v-else />
      <Icon name="solar:scissors-outline" class="icon" />
      <Icon name="ic:sharp-shopping-bag" class="icon" />
    </navbar>
    <div class="menu" @click="this.menu = !this.menu" :class="menu ? '' : 'close'">

    </div>
    <swiper :modules="this.modules" :speed="500" :keyboard="{
      enabled: true,
    }" :slidesPerView="1" :direction="'vertical'" :mousewheel="true" class="swipe">
      <swiper-slide class="frame">
        <img src="../assets/2 pexels-dương-nhân-1529881.jpg" alt="" class="image">
      </swiper-slide>
      <swiper-slide class="frame">
        <img class="image" src="../assets/1 pexels-alan-cabello-1291515.jpg" alt="">
      </swiper-slide>
      <swiper-slide class="frame">Slide 3</swiper-slide>

    </swiper>
  </div>
</template>

<script>
import { Swiper, SwiperSlide } from 'swiper/vue';
import { Mousewheel, Keyboard } from 'swiper/modules';
// import 'swiper/css';

export default {
  components: {
    Swiper,
    SwiperSlide,
  },
  data() {
    return {
      modules: [Mousewheel, Keyboard],
      menu: false,

    };
  }
}


</script>

<style lang="scss" scoped>
.navbar {
  position: absolute;
  display: flex;
  justify-content: space-between;
  align-items: center;
  top: 20px;
  right: 0;
  left: 0;
  bottom: auto;
  
  .icon {
    z-index: 10;
    font-size: 40px;
    color: white;
  }

  .closeIcon {
    z-index: 30;
    color: black !important;
  }
}

.menu {
  position: absolute;
  left: 0;
  top: 0;
  bottom: 0;
  width: 90%;
  height: 100vh;
  z-index: 20;
  background-color: whitesmoke;
  transition: 400ms ease;
}

.close {
  width: 0;
}

.swipe {
  width: 100%;
  height: 100vh;

  .frame {
    position: relative;
    width: 100%;
    height: 100vh;

    .image {
      position: absolute;
      bottom: 0;
      top: 0;
      right: 0;
      width: 100%;
      height: 100%;
      // background-color: #000;
      background-position: center center;
      background-size: contain;
      object-fit: cover;
      z-index: 0;
    }
  }
}
</style>