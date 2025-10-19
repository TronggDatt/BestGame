<template>
  <div class="p-4 overflow-x-auto">
    <table class="min-w-full border border-gray-300">
      <thead class="bg-gray-200">
        <tr>
          <th class="px-4 py-2 border">Top</th>
          <th class="px-4 py-2 border">Avatar</th>
          <th class="px-4 py-2 border">Description</th>
          <th class="px-4 py-2 border">Jogo</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(game, index) in games" :key="index" class="hover:bg-gray-50">
          <!-- Cột 1: hình top game -->
          <td class="px-4 py-2 border">
            <img :src="game.topImage" alt="Top" class="w-16 h-16 object-cover rounded" />
          </td>

          <!-- Cột 2: avatar game -->
          <td class="px-4 py-2 border">
            <img :src="game.avatar" alt="Avatar" class="w-12 h-12 object-cover rounded-full" />
          </td>

          <!-- Cột 3: GameItem -->
          <td class="px-4 py-2 border">
            <GameItem :game="game" />
          </td>

          <!-- Cột 4: Button -->
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
import GameItem from './GameItem.vue';

export default {
  name: "GameList",
  components: { GameItem },
  props: {
    games: { type: Array, required: true }
  }
}
</script>
