<template>
  <div class="flex justify-center bg-gray-100 min-h-screen">
      <div class="header w-full">
        <img 
          src="../src/assets/header.png" 
          alt="header" 
          class="h-20 w-auto mx-auto object-contain"
        />
      </div>


    <div class="w-full max-w-sm bg-white mt-20 relative shadow">
      <main>
        <carousel :slides="slides"></carousel>
         <h2 class="mt-4 text-center font-bold text-lg">Melhores sites de cassino no Brasil</h2>
        <GameList :games="games" />
      </main>
    </div>

  </div>
</template>

<script>
import Carousel from '../src/components/AppCarousel.vue';
import GameList from '../src/components/GameList.vue';

export default {
  name: 'App',
  components: { Carousel, GameList },
  data: () => ({
    slides: [
      { src: require("../src/assets/banner1.gif"), alt: "Banner 1" },
      { src: require("../src/assets/banner2.gif"), alt: "Banner 2" },
    ],
    games: [
  {
    // topImage: require("../src/assets/top1.jpg"),
    avatar: require("../src/assets/game1.png"),
    // name: "Game 1",
    stars: 1,
    note: "Ghi chú Game 1",
    link: "https://example.com/game1"
  },
  {
    // topImage: require("../src/assets/top2.jpg"),
    avatar: require("../src/assets/game2.jpg"),
    // name: "Game 2",
    // stars: 1,
    note: "Ghi chú Game 2",
    link: "https://example.com/game2"
  }
]
  }),
}
</script>

<style scoped>
.header {
  position: fixed;
  top: 0;
  left: 50%;
  transform: translateX(-50%);
  z-index: 1000;
  display: flex;
  justify-content: center;
  align-items: center;

}
.header img {
   width: 110%;      
  height: auto;    
  object-fit: contain;
}
</style>

<style>
body {
  margin: 30px;
  background-color: #f3f4f6;
}
</style>
