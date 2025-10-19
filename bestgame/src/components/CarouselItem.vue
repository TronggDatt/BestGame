<template>
  <transition name="slide-in">
    <div class="carousel-item" v-show="currentSlide === index">
      <img :src="slide.src" class="mx-auto" />
    </div>
  </transition>
</template>

<script>
export default {
  // name: 'CarouselItem',
  props: ['slide', 'currentSlide', 'index']
}
</script>

<style scoped>
.carousel-item {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  display: flex;
  justify-content: center;
  align-items: center;
}
.slide-in-enter-active, .slide-in-leave-active {
  transition: all 1s ease-in-out;
}
.slide-in-enter-from {
  transform: translate(100%);
}
.slide-in-leave-to {
  transform: translate(-100%);
}
/* .carousel-item img {
  width: 100%;
  height: auto;
  object-fit: contain;
} */
</style>
