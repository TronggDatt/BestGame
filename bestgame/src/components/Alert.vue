<template>
  <transition name="slide-up">
    <div v-if="visible" class="fixed bottom-4 left-1/2 transform -translate-x-1/2 bg-white shadow-lg rounded-lg flex items-center p-4 space-x-4 z-50 w-full max-w-md">
      
      <img :src="image" alt="Alert Image" class="w-12 h-12 object-cover rounded" />

      <div class="flex-1">
        <h3 class="font-semibold text-gray-800 text-sm sm:text-base">{{ title }}</h3>
        <p class="text-gray-600 text-xs sm:text-sm">{{ description }}</p>
      </div>

      <div class="flex space-x-2">
        <button @click="closeAlert" class="bg-gray-300 hover:bg-gray-400 text-gray-800 px-3 py-1 rounded text-xs sm:text-sm">
          Cancel
        </button>
        <a :href="installLink" target="_blank" class="bg-green-600 hover:bg-green-700 text-white px-3 py-1 rounded text-xs sm:text-sm">
          Install
        </a>
      </div>

    </div>
  </transition>
</template>

<script>
export default {
  name: "BottomAlert",
  props: {
    title: { type: String, default: "Game mới đã có!" },
    description: { type: String, default: "Tải ngay để trải nghiệm." },
    image: { type: String, default: "/src/assets/game1.png" },
    installLink: { type: String, default: "#" },
    duration: { type: Number, default: 10000 } 
  },
  data() {
    return { visible: true };
  },
  mounted() {
    setTimeout(() => this.visible = false, this.duration);
  },
  methods: {
    closeAlert() {
      this.visible = false;
    }
  }
}
</script>

<style scoped>
.slide-up-enter-active, .slide-up-leave-active {
  transition: all 0.3s ease;
}
.slide-up-enter-from, .slide-up-leave-to {
  transform: translateY(100%);
  opacity: 0;
}
</style>
