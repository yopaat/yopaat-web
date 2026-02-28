<script setup lang="ts">
useSeoMeta({
  title: 'Gésumé — Yopaat',
  description: 'Gésumé is an innovative job-board and recruitment platform by Yopaat that ensures effective matches between professionals and vacancies through smart technology.',
  keywords: 'Gésumé, job board, recruitment platform, talent matching, professionals, recruiters, Yopaat',
  ogTitle: 'Gésumé — Smart Recruitment Platform by Yopaat',
  ogDescription: 'Innovative job-board and recruitment platform ensuring effective matches between professionals and vacancies.',
  ogImage: 'https://gesume.com/gesume-logo.png',
  ogType: 'website',
  ogUrl: 'https://yopaat.com/products/gesume',
  twitterCard: 'summary_large_image',
  twitterTitle: 'Gésumé — Smart Recruitment Platform by Yopaat',
  twitterDescription: 'Innovative job-board and recruitment platform ensuring effective matches between professionals and vacancies.',
  twitterImage: 'https://gesume.com/gesume-logo.png',
  twitterSite: '@yopaat'
})
</script>

<template>
  <div>
    <!-- ── HERO ─────────────────────────────────────────────── -->
    <section class="relative py-28 overflow-hidden">
      <div class="absolute inset-0 pointer-events-none">
        <div class="absolute top-0 left-1/3 w-[500px] h-[500px] rounded-full bg-primary/8 blur-[130px] animate-slow-pulse" />
        <div class="absolute bottom-0 right-1/4 w-[400px] h-[400px] rounded-full bg-indigo-500/8 blur-[110px] animate-slow-pulse animation-delay-1000" />
        <div
          class="absolute inset-0 opacity-20"
          style="background-image: radial-gradient(circle, rgb(148 163 184 / 0.4) 1px, transparent 1px); background-size: 36px 36px;"
        />
      </div>

      <UContainer class="relative">
        <div class="max-w-3xl mx-auto text-center">
          <!-- Breadcrumb -->
          <div class="flex items-center justify-center gap-2 text-sm text-muted mb-10 animate-fade-in">
            <NuxtLink
              to="/products"
              class="hover:text-foreground transition-colors"
            >Products</NuxtLink>
            <UIcon
              name="i-lucide-chevron-right"
              class="w-3 h-3"
            />
            <span>Gésumé</span>
          </div>

          <!-- Gesume logo -->
          <div class="flex justify-center mb-10 animate-fade-in-up">
            <a
              href="https://gesume.com/"
              target="_blank"
              rel="noopener noreferrer"
              class="block p-6 rounded-2xl border border-default bg-default hover:border-primary/30 hover:shadow-xl hover:shadow-primary/10 transition-all duration-300"
            >
              <img
                src="https://gesume.com/gesume-logo.png"
                alt="Gésumé"
                width="228"
                height="81"
                class="h-16 w-auto object-contain dark:hidden"
              >
              <img
                src="https://gesume.com/gesume-logo-light.png"
                alt="Gésumé"
                width="228"
                height="81"
                class="h-16 w-auto object-contain hidden dark:block"
              >
            </a>
          </div>

          <!-- Description -->
          <p class="text-xl md:text-2xl text-muted font-light leading-relaxed mb-10 animate-fade-in-up animation-delay-200">
            Gésumé is a very innovative job-board and recruitment platform that helps professionals
            and recruiters ensure
            <span class="text-foreground font-medium">effective matches between individuals and vacancies.</span>
          </p>

          <!-- CTA -->
          <div class="flex flex-wrap items-center justify-center gap-4 animate-fade-in-up animation-delay-400">
            <UButton
              to="https://gesume.com/"
              target="_blank"
              rel="noopener noreferrer"
              size="xl"
              class="rounded-full px-8 font-semibold shadow-lg shadow-primary/20"
              trailing-icon="i-lucide-external-link"
            >
              Visit gesume.com
            </UButton>
            <UButton
              to="/products"
              size="xl"
              color="neutral"
              variant="outline"
              class="rounded-full px-8 font-semibold"
              leading-icon="i-lucide-arrow-left"
            >
              Back to Products
            </UButton>
          </div>
        </div>
      </UContainer>
    </section>

    <!-- ── HIGHLIGHTS ─────────────────────────────────────────── -->
    <section class="py-20 bg-elevated">
      <UContainer>
        <div class="grid grid-cols-1 sm:grid-cols-3 gap-6 max-w-3xl mx-auto">
          <div
            v-for="feature in [
              { icon: 'i-lucide-users', title: 'For Professionals', body: 'Build and manage your professional profile to stand out to the right recruiters.' },
              { icon: 'i-lucide-search', title: 'Smart Matching', body: 'Innovative algorithms ensure effective matches between individuals and vacancies.' },
              { icon: 'i-lucide-briefcase', title: 'For Recruiters', body: 'Find the right candidates faster with precise, data-driven talent matching.' }
            ]"
            :key="feature.title"
            class="scroll-reveal rounded-2xl border border-default bg-default p-6 flex flex-col gap-4
                   hover:border-primary/30 hover:shadow-lg hover:shadow-primary/10 hover:-translate-y-1 transition-all duration-300"
          >
            <div class="w-11 h-11 rounded-xl bg-primary/10 flex items-center justify-center shrink-0">
              <UIcon
                :name="feature.icon"
                class="w-5 h-5 text-primary"
              />
            </div>
            <h2 class="font-semibold text-base">
              {{ feature.title }}
            </h2>
            <p class="text-muted text-sm leading-relaxed">
              {{ feature.body }}
            </p>
          </div>
        </div>
      </UContainer>
    </section>
  </div>
</template>
