<template>
  <div class="p-4 overflow-x-auto">
    <table class="min-w-full border border-gray-300">
      <thead class="bg-gray-200">
        <tr>
          <th class="px-4 py-2 border"></th>
          <th class="px-4 py-2 border"></th>
          <th class="px-4 py-2 border"></th>
          <th class="px-4 py-2 border"></th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(game, index) in games" :key="index" class="hover:bg-gray-50">
          <!-- C1: hình top game -->
          <td class="px-4 py-2 border">
            <img :src="game.topImage" alt="Top" class="w-16 h-16 object-cover rounded" />
          </td>

          <!-- C2: avatar game -->
          <td class="px-4 py-2 border">
            <img :src="game.avatar" alt="Avatar" class="w-12 h-12 object-cover rounded-full" />
          </td>

          <!-- C3: GameItem -->
          <td class="px-4 py-2 border">
      <div class="flex flex-col space-y-1">
        <!-- H1: Tên game -->
        <h3 class="font-semibold text-gray-800 text-sm">{{ game.name }}</h3>

        <!-- H2: Star -->
        <div class="flex items-center">
          <span
            v-for="n in 5"
            :key="n"
            class="text-yellow-400 text-lg"
          >
            {{ n <= game.stars ? '★' : '☆' }}
          </span>
        </div>

        <!-- H3: Ghi chú -->
        <p class="text-xs text-gray-500">{{ game.note }}</p>
      </div>
    </td>

          <!-- C4: Button -->
          <td class="px-4 py-2 border">
            <a :href="game.link" target="_blank" class="bg-green-600 text-white px-3 py-1 rounded hover:bg-green-700 text-xs sm:text-sm">
              Jogo
            </a>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
// import GameItem from './GameItem.vue';

export default {
  name: "GameList",
//   components: { GameItem },
  props: {
    games: { type: Array, required: true }
  }
}
</script>

<style scoped>
table {
  margin: 0 auto; /* Căn giữa */
  max-width: 900px;
}
</style>
