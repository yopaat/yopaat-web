<template>
  <div class="relative min-h-[calc(100vh-140px)] flex items-center justify-center overflow-hidden">
    <div class="absolute top-4 right-4 z-50">
      <UColorModeSwitch />
    </div>

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
      <div class="relative group cursor-default mb-8">
        <div class="absolute inset-0 bg-linear-to-r from-blue-500/30 to-purple-600/30 rounded-full blur-3xl opacity-0 group-hover:opacity-100 transition-opacity duration-1000" />
        <UColorModeImage
          light="/yopaat-logo-light.png"
          dark="/yopaat-logo.png"
          alt="Yopaat Logo"
          class="relative w-40 h-40 md:w-56 md:h-56 object-contain drop-shadow-2xl transform transition-transform duration-700 group-hover:scale-105"
        />
      </div>

      <!-- Main Content -->
      <div class="space-y-6 max-w-4xl mx-auto">
        <h1 class="text-4xl md:text-6xl lg:text-7xl font-black tracking-tighter text-transparent bg-clip-text bg-linear-to-br from-gray-900 via-gray-700 to-gray-500 dark:from-white dark:via-gray-100 dark:to-gray-400 drop-shadow-sm pb-2">
          Technology & <br>
          <span class="text-transparent bg-clip-text bg-linear-to-r from-blue-600 to-purple-600 dark:from-blue-400 dark:to-purple-400">
            Management Services
          </span>
        </h1>

        <div class="text-lg md:text-xl text-gray-600 dark:text-gray-300 font-light max-w-3xl mx-auto leading-relaxed space-y-6 text-left">
          <p class="text-center font-medium">
            Yopaat is a cross-industry, cross-disciplinary B2B services company with a focus on Information & Communication Technologies.
          </p>

          <div class="bg-white/30 dark:bg-gray-800/30 p-6 md:p-8 rounded-2xl border border-gray-200/50 dark:border-gray-700/50 shadow-sm backdrop-blur-sm relative">
            <div class="absolute -top-3 left-8 bg-blue-500/10 text-blue-600 dark:text-blue-400 px-3 py-1 rounded-full text-xs font-bold uppercase tracking-wider border border-blue-500/20 backdrop-blur-md">
              About Us
            </div>
            <p class="text-base text-gray-500 dark:text-gray-400 leading-relaxed pt-2">
              Yopaat takes its name from the ancient Mayan storm god. Its relevance is inspiring since we are all taken by the storm of technological change and being able to manage that change is the ultimate power.
            </p>
            <p class="text-base text-gray-500 dark:text-gray-400 leading-relaxed mt-4">
              Yopaat excels in putting skills and specializations of various fields into a coherent, coordinated action plan in order to meet and exceed client expectations. A deep understanding in an industry enables not only getting client needs right but also taking a client by hand to expand their horizons to have a extended view in their initially assumed set of needs.
            </p>
            <p class="text-base text-gray-500 dark:text-gray-400 leading-relaxed mt-4">
              Yopaat's capabilities bring a verticalized articulation of technological prowess. Yopaat's clients have been benefiting from established industry standards and proven best practices, out of the box.
            </p>
          </div>
        </div>
      </div>

      <!-- Call to action / Status -->
      <div class="mt-12">
        <div class="inline-flex items-center gap-4 px-6 py-3 rounded-full bg-white/50 dark:bg-gray-800/50 border border-gray-200 dark:border-gray-700/50 backdrop-blur-md shadow-lg transition-transform hover:scale-105 duration-300">
          <span class="relative flex h-3 w-3">
            <span class="animate-ping absolute inline-flex h-full w-full rounded-full bg-blue-500 opacity-75" />
            <span class="relative inline-flex rounded-full h-3 w-3 bg-blue-500" />
          </span>
          <span class="text-xs md:text-sm font-bold tracking-widest text-gray-800 dark:text-gray-200 uppercase">
            Platform Coming Soon
          </span>
        </div>
      </div>

      <!-- Progress Bar Decoration -->
      <div class="w-64 h-1 bg-gray-200 dark:bg-gray-800 rounded-full mt-16 overflow-hidden shadow-inner">
        <div class="h-full bg-linear-to-r from-blue-500 to-purple-600 w-1/3 animate-pulse rounded-full relative">
          <div class="absolute inset-0 bg-white/30 truncate" />
        </div>
      </div>
    </UContainer>
  </div>
</template>

<script setup>
useSeoMeta({
  title: 'Yopaat - Technology & Management Services',
  description: 'Yopaat is a cross-industry, cross-disciplinary B2B services company with a focus on technology and management services in Information & Communication Technologies.',
  keywords: 'Yopaat, B2B services, technology, management services, Information & Communication Technologies',
  ogTitle: 'Yopaat - Technology & Management Services',
  ogDescription: 'Yopaat excels in putting skills and specializations of various fields into a coherent, coordinated action plan in order to meet and exceed client expectations.',
  ogImage: '/yopaat-logo.png',
  twitterImage: '/yopaat-logo.png',
  twitterCard: 'summary_large_image'
})
</script>
