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
         <h2 class="title">
          Melhores sites de cassino no Brasil
        </h2>
        <GameList :games="games" />
      </main>
    </div>

    <BottomAlert
      title="Baixe o aplicativo Bestgame na tela inicial agora e ganhe um bônus de 77 reais.!"
      description="Trải nghiệm phiên bản mới nhất ngay bây giờ."
      image="../src/assets/game1.png"
      installLink="https://example.com/game1.apk"
      :duration="10000"
    />

  </div>
</template>

<script>
import Carousel from '../src/components/AppCarousel.vue';
import GameList from '../src/components/GameList.vue';
import BottomAlert from '../src/components/Alert.vue';

export default {
  name: 'App',
  components: { Carousel, GameList, BottomAlert },
  data: () => ({
    slides: [
      { src: require("../src/assets/banner1.gif"), alt: "Banner 1" },
      { src: require("../src/assets/banner2.gif"), alt: "Banner 2" },
    ],
    games: [
  {
    topImage: require("../src/assets/top1.png"),
    avatar: require("../src/assets/game1.png"),
    name: "Minecraft",
    stars: 4,
    note: "Grande variedade de slots com alta taxa de ganho e saques instantâneos. Ideal para quem busca emoção e agilidade.",
    link: "https://example.com/game1"
  },
  {
    topImage: require("../src/assets/top2.png"),
    avatar: require("../src/assets/game2.jpg"),
    name: "Superman",
    stars: 3,
    note: "Game 2",
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

.title {
  margin: 1rem 0;
  text-align: center;
  font-size: 1.25rem;
  font-weight: bold;
}
</style>

<style>
body {
  margin: 40px;
  background-color: #f3f4f6;
}
</style>
