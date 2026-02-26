<template>
  <div class="relative min-h-[calc(100vh-140px)] flex items-center justify-center overflow-hidden">
    <!-- Dynamic Background Elements -->
    <div class="absolute inset-0 z-0 overflow-hidden pointer-events-none">
      <div
        class="absolute top-1/4 left-1/4 w-120 h-120 bg-indigo-500/10 rounded-full blur-[120px] mix-blend-screen animate-pulse"
        style="animation-duration: 4s;"
      />
      <div
        class="absolute bottom-1/4 right-1/4 w-120 h-120 bg-purple-500/10 rounded-full blur-[120px] mix-blend-screen animate-pulse"
        style="animation-duration: 5s; animation-delay: 2s;"
      />
      <!-- Dotted grid effect -->
      <div class="absolute inset-0 bg-[url('data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iNDAiIGhlaWdodD0iNDAiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+PGNpcmNsZSBjeD0iMSIgY3k9IjEiIHI9IjEiIGZpbGw9InJnYmEoMTI4LCAxMjgsIDEyOCwgMC4yKSIvPjwvc3ZnPg==')] opacity-50 mask-[radial-gradient(circle_at_center,white,transparent_80%)]" />
    </div>

    <UContainer class="relative z-10 flex flex-col items-center justify-center text-center py-20 px-4">
      <!-- Logo Animation -->
      <div class="relative group cursor-default mb-12">
        <div class="absolute inset-0 bg-linear-to-r from-blue-500/30 to-purple-600/30 rounded-full blur-3xl opacity-0 group-hover:opacity-100 transition-opacity duration-1000" />
        <img
          src="/yopaat-logo.png"
          alt="Yopaat Logo"
          class="relative w-48 h-48 md:w-64 md:h-64 object-contain drop-shadow-2xl transform transition-transform duration-700 group-hover:scale-105"
        >
      </div>

      <!-- Main Content -->
      <div class="space-y-8 max-w-4xl mx-auto">
        <h1 class="text-5xl md:text-7xl lg:text-8xl font-black tracking-tighter text-transparent bg-clip-text bg-linear-to-br from-gray-900 via-gray-700 to-gray-500 dark:from-white dark:via-gray-100 dark:to-gray-400 drop-shadow-sm pb-2">
          Something Epic<br>
          <span class="text-transparent bg-clip-text bg-linear-to-r from-blue-600 to-purple-600 dark:from-blue-400 dark:to-purple-400">
            Is Coming Soon
          </span>
        </h1>

        <p class="text-xl md:text-2xl text-gray-500 dark:text-gray-400 font-light max-w-2xl mx-auto leading-relaxed">
          We are crafting a beautiful new digital experience.
          Our new website is currently a work in progress, but we can't wait to share it with you.
        </p>
      </div>

      <!-- Call to action / Status -->
      <div class="mt-16">
        <div class="inline-flex items-center gap-4 px-8 py-4 rounded-full bg-white/50 dark:bg-gray-800/50 border border-gray-200 dark:border-gray-700/50 backdrop-blur-md shadow-lg transition-transform hover:scale-105 duration-300">
          <span class="relative flex h-4 w-4">
            <span class="animate-ping absolute inline-flex h-full w-full rounded-full bg-blue-500 opacity-75" />
            <span class="relative inline-flex rounded-full h-4 w-4 bg-blue-500" />
          </span>
          <span class="text-sm md:text-base font-bold tracking-widest text-gray-800 dark:text-gray-200 uppercase">
            Work in Progress
          </span>
        </div>
      </div>

      <!-- Progress Bar Decoration -->
      <div class="w-64 h-1.5 bg-gray-200 dark:bg-gray-800 rounded-full mt-20 overflow-hidden shadow-inner">
        <div class="h-full bg-linear-to-r from-blue-500 to-purple-600 w-1/3 animate-pulse rounded-full relative">
          <div class="absolute inset-0 bg-white/30 truncate" />
        </div>
      </div>
    </UContainer>
  </div>
</template>

<script setup>
useSeoMeta({
  title: 'Coming Soon - Yopaat',
  description: 'We are crafting a beautiful new digital experience. Our new website is currently a work in progress.'
})
</script>
