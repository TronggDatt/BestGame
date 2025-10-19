<template>
  <div class="carousel">
    <div class="carousel-inner">
      <div class="carousel-item">
        <carousel-item 
        v-for="(slide, index) in slides" 
        :slide="slide"
        :key="`item-${index}`" 
        :current-slide="currentSlide"
        :index="index"
        ></carousel-item>
      </div>
    </div>
  </div>
</template>

<script>    
import CarouselItem from './CarouselItem.vue';
export default {
  name: 'AppCarousel',
  components: {
    CarouselItem
  },

  data: () => ({
    slides: [
      { src: require("../assets/banner1.gif"), alt: "Banner 1" },
      { src: require("../assets/banner2.gif"), alt: "Banner 2" }
    ],
    currentSlide: 0,
    slideInterval: null
  }),
  methods:{
    setCurrentSlide(index){
        this.currentSlide = index;
    }
  },

  mounted(){
  this.slideInterval = setInterval(() => {
    const index = this.currentSlide < this.slides.length - 1 
      ? this.currentSlide + 1 
      : 0;
    this.setCurrentSlide(index);
  }, 3000);
},
  beforeUnmount(){
    clearInterval(this.slideInterval);
  }

}
</script>

<style scoped>
.carousel {
    display: flex;
    justify-content: center;
}
.carousel-inner {
  position: relative;
  width: 900%;
  height: 400px;
  overflow: hidden;
}

</style>