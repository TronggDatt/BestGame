<template>
  <div class="flex flex-col gap-1">
    <!-- Hàng 1: tên game -->
    <span class="font-semibold text-sm sm:text-base">Minecraft</span>

    <!-- Hàng 2: star rating -->
    <div class="flex items-center gap-1">
      <span v-for="i in 5" :key="i">
        <svg v-if="i <= game.stars" class="w-4 h-4 text-yellow-400" fill="currentColor" viewBox="0 0 20 20">
          <!-- <path d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.286 3.955a1 1 0 00.95.69h4.157c.969 0 1.371 1.24.588 1.81l-3.37 2.448a1 1 0 00-.364 1.118l1.286 3.955c.3.921-.755 1.688-1.538 1.118l-3.37-2.448a1 1 0 00-1.175 0l-3.37 2.448c-.783.57-1.838-.197-1.538-1.118l1.286-3.955a1 1 0 00-.364-1.118L2.028 9.382c-.783-.57-.38-1.81.588-1.81h4.157a1 1 0 00.95-.69l1.286-3.955z"/> -->
        </svg>
        <svg v-else class="w-4 h-4 text-gray-300" fill="currentColor" viewBox="0 0 20 20">
          <!-- <path d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.286 3.955a1 1 0 00.95.69h4.157c.969 0 1.371 1.24.588 1.81l-3.37 2.448a1 1 0 00-.364 1.118l1.286 3.955c.3.921-.755 1.688-1.538 1.118l-3.37-2.448a1 1 0 00-1.175 0l-3.37 2.448c-.783.57-1.838-.197-1.538-1.118l1.286-3.955a1 1 0 00-.364-1.118L2.028 9.382c-.783-.57-.38-1.81.588-1.81h4.157a1 1 0 00.95-.69l1.286-3.955z"/> -->
        </svg>
      </span>
    </div>

    <!-- Hàng 3: ghi chú -->
    <span class="text-gray-600 text-xs sm:text-sm">Superman</span>
  </div>
</template>

<script>
export default {
  name: "GameItem",
  props: {
    game: { type: Object, required: true }
  }
}
</script>
