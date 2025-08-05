<template>
  <div class="item-card flex flex-col items-center gap-2 rounded bg-[#1e1e1f] border border-[#383838] rounded-xl text-blue-50 md:gap-3 px-5 py-5 lg:px-5 h-full">
    <!-- Skeleton Image -->
    <div class="w-full aspect-video bg-gray-700 rounded-xl animate-pulse"></div>
    <!-- Skeleton Title -->
    <div class="w-full flex flex-col gap-2 items-center text-sm md:text-base lg:text-lg flex-grow">
      <div class="w-3/4 h-6 bg-gray-700 rounded animate-pulse"></div>
      <!-- Skeleton Description -->
      <div class="w-full flex flex-col gap-2">
        <div class="w-full h-3 bg-gray-700 rounded animate-pulse"></div>
        <div class="w-4/5 h-3 bg-gray-700 rounded animate-pulse"></div>
        <div class="w-5/6 h-3 bg-gray-700 rounded animate-pulse"></div>
      </div>
      <!-- Skeleton Tech Stack -->
      <div class="w-full mt-auto pt-4">
        <div class="w-2/5 h-4 bg-gray-700 rounded animate-pulse"></div>
      </div>
      <!-- Skeleton Links -->
      <div class="w-full flex justify-end gap-2 mt-2">
        <div class="w-5 h-5 bg-gray-700 rounded animate-pulse"></div>
        <div class="w-5 h-5 bg-gray-700 rounded animate-pulse"></div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'SkeletonCard'
}
</script>

<style scoped>
/* Inherit styles from parent component if needed */
</style>