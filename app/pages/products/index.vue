<script setup lang="ts">
useSeoMeta({
  title: 'Products — Yopaat',
  description: 'Discover Yopaat\'s product portfolio including Gésumé, an innovative job-board and recruitment platform ensuring effective matches between professionals and vacancies.',
  keywords: 'Yopaat products, Gésumé, job board, recruitment platform, talent matching, HR technology',
  ogTitle: 'Products — Yopaat',
  ogDescription: 'Purpose-built technology products from Yopaat — built for the real world.',
  ogImage: 'https://yopaat.com/yopaat-logo.png',
  ogType: 'website',
  ogUrl: 'https://yopaat.com/products',
  twitterCard: 'summary_large_image',
  twitterTitle: 'Products — Yopaat',
  twitterDescription: 'Innovative technology products from Yopaat, including Gésumé — the smart job-board and recruitment platform.',
  twitterImage: 'https://yopaat.com/yopaat-logo.png',
  twitterSite: '@yopaat'
})

const products = [
  {
    name: 'Gésumé',
    href: '/products/gesume',
    externalHref: 'https://gesume.com/',
    tagline: 'Smart Job-Board & Recruitment Platform',
    description:
      'Gésumé is a very innovative job-board and recruitment platform that helps professionals and recruiters ensure effective matches between individuals and vacancies.',
    features: [
      { icon: 'i-lucide-users', label: 'For Professionals', body: 'Build and manage your professional profile to stand out to the right recruiters.' },
      { icon: 'i-lucide-sparkles', label: 'Smart Matching', body: 'Innovative algorithms ensure effective matches between individuals and vacancies.' },
      { icon: 'i-lucide-briefcase', label: 'For Recruiters', body: 'Find the right candidates faster with precise, data-driven talent matching.' }
    ],
    badge: 'Live',
    badgeColor: 'text-emerald-400 bg-emerald-400/10 border-emerald-400/30'
  }
]

onMounted(() => {
  const observer = new IntersectionObserver(
    entries => entries.forEach((el) => {
      if (el.isIntersecting) {
        el.target.classList.add('revealed')
        observer.unobserve(el.target)
      }
    }),
    { threshold: 0.1 }
  )
  document.querySelectorAll('.scroll-reveal').forEach(el => observer.observe(el))
})
</script>

<template>
  <div>
    <!-- ── HERO ──────────────────────────────────────────────── -->
    <section class="relative py-28 overflow-hidden">
      <div class="absolute inset-0 pointer-events-none">
        <div class="absolute top-0 left-1/3 w-[500px] h-[500px] rounded-full bg-primary/8 blur-[130px] animate-slow-pulse" />
        <div class="absolute bottom-0 right-1/4 w-[400px] h-[400px] rounded-full bg-indigo-500/8 blur-[110px] animate-slow-pulse animation-delay-1000" />
        <div
          class="absolute inset-0 opacity-20"
          style="background-image: radial-gradient(circle, rgb(148 163 184 / 0.4) 1px, transparent 1px); background-size: 36px 36px;"
        />
      </div>

      <UContainer class="relative text-center">
        <div class="animate-fade-in-up">
          <h1 class="text-4xl sm:text-5xl md:text-6xl font-bold leading-[1.15] mb-6 max-w-3xl mx-auto">
            <span class="font-light text-muted">Built by Yopaat,</span><br>
            made for the
            <span class="text-transparent bg-clip-text bg-linear-to-r from-blue-500 to-indigo-600"> real world.</span>
          </h1>

          <p class="text-lg md:text-xl text-muted font-light leading-relaxed max-w-2xl mx-auto">
            Our products are born from deep industry experience and a passion for solving real
            problems with elegant technology — designed to deliver value from day one.
          </p>
        </div>
      </UContainer>
    </section>

    <!-- ── PRODUCT SHOWCASE ──────────────────────────────────── -->
    <section class="py-24 bg-elevated">
      <UContainer>
        <div class="text-center mb-16 scroll-reveal">
          <p class="text-sm font-semibold text-primary tracking-widest uppercase mb-3">
            Our Portfolio
          </p>
          <h2 class="text-3xl md:text-4xl font-bold mb-4">
            Products
          </h2>
          <p class="text-muted max-w-xl mx-auto text-lg font-light">
            Purpose-built platforms crafted with the same rigour and expertise we bring to every client engagement.
          </p>
        </div>

        <!-- Gésumé card -->
        <div
          v-for="product in products"
          :key="product.name"
          class="scroll-reveal mb-10 last:mb-0"
        >
          <div class="rounded-3xl border border-default bg-default shadow-xl overflow-hidden">
            <div class="grid grid-cols-1 lg:grid-cols-2">
              <!-- Left: content -->
              <div class="p-10 lg:p-14 flex flex-col justify-between gap-8">
                <!-- Header row -->
                <div>
                  <div class="flex items-center gap-3 mb-6">
                    <!-- Logo -->
                    <a
                      :href="product.externalHref"
                      target="_blank"
                      rel="noopener noreferrer"
                      class="block"
                    >
                      <!-- Light theme logo (dark text) -->
                      <img
                        src="https://gesume.com/gesume-logo.png"
                        alt="Gésumé"
                        width="228"
                        height="81"
                        class="h-10 w-auto object-contain dark:hidden"
                      >
                      <!-- Dark theme logo (light text) -->
                      <img
                        src="https://gesume.com/gesume-logo-light.png"
                        alt="Gésumé"
                        width="228"
                        height="81"
                        class="h-10 w-auto object-contain hidden dark:block"
                      >
                    </a>
                    <!-- Status badge -->
                    <span
                      class="inline-flex items-center gap-1.5 text-xs font-semibold px-2.5 py-1 rounded-full border"
                      :class="product.badgeColor"
                    >
                      <span class="w-1.5 h-1.5 rounded-full bg-emerald-400 animate-pulse inline-block" />
                      {{ product.badge }}
                    </span>
                  </div>

                  <p class="text-xs font-semibold text-primary tracking-widest uppercase mb-2">
                    {{ product.tagline }}
                  </p>

                  <p class="text-muted text-lg leading-relaxed max-w-md">
                    {{ product.description }}
                  </p>
                </div>

                <!-- Feature list -->
                <div class="grid grid-cols-1 sm:grid-cols-3 gap-4">
                  <div
                    v-for="feature in product.features"
                    :key="feature.label"
                    class="rounded-2xl border border-default bg-elevated p-5 flex flex-col gap-3 hover:border-primary/30 hover:shadow-md transition-all duration-300"
                  >
                    <div class="w-9 h-9 rounded-xl bg-primary/10 flex items-center justify-center shrink-0">
                      <UIcon
                        :name="feature.icon"
                        class="w-4.5 h-4.5 text-primary"
                      />
                    </div>
                    <div>
                      <p class="font-semibold text-sm mb-1">
                        {{ feature.label }}
                      </p>
                      <p class="text-muted text-xs leading-relaxed">
                        {{ feature.body }}
                      </p>
                    </div>
                  </div>
                </div>

                <!-- CTAs -->
                <div class="flex flex-wrap gap-3">
                  <UButton
                    :to="product.externalHref"
                    target="_blank"
                    rel="noopener noreferrer"
                    size="lg"
                    class="rounded-full px-7 font-semibold shadow-lg shadow-primary/20"
                    trailing-icon="i-lucide-external-link"
                  >
                    Visit gesume.com
                  </UButton>
                  <UButton
                    :to="product.href"
                    size="lg"
                    color="neutral"
                    variant="outline"
                    class="rounded-full px-7 font-semibold"
                    trailing-icon="i-lucide-arrow-right"
                  >
                    Learn More
                  </UButton>
                </div>
              </div>

              <!-- Right: visual panel -->
              <div class="relative bg-slate-900 min-h-[320px] lg:min-h-0 flex items-center justify-center overflow-hidden">
                <!-- bg glow -->
                <div class="absolute inset-0 pointer-events-none">
                  <div class="absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 w-[400px] h-[400px] rounded-full bg-primary/25 blur-[100px]" />
                </div>
                <div
                  class="absolute inset-0 opacity-10"
                  style="background-image: radial-gradient(circle, rgb(255 255 255 / 0.5) 1px, transparent 1px); background-size: 32px 32px;"
                />

                <!-- Floating stat cards -->
                <div class="relative z-10 flex flex-col items-center gap-5 px-10 py-12">
                  <div class="grid grid-cols-2 gap-4 w-full max-w-xs">
                    <div class="rounded-2xl border border-white/10 bg-white/5 backdrop-blur-sm p-4 text-center">
                      <p class="text-2xl font-bold text-white">
                        10K+
                      </p>
                      <p class="text-white/50 text-xs mt-0.5">
                        Professionals
                      </p>
                    </div>
                    <div class="rounded-2xl border border-white/10 bg-white/5 backdrop-blur-sm p-4 text-center">
                      <p class="text-2xl font-bold text-white">
                        500+
                      </p>
                      <p class="text-white/50 text-xs mt-0.5">
                        Recruiters
                      </p>
                    </div>
                    <div class="rounded-2xl border border-white/10 bg-white/5 backdrop-blur-sm p-4 text-center col-span-2">
                      <p class="text-2xl font-bold text-white">
                        Smart Matching
                      </p>
                      <p class="text-white/50 text-xs mt-0.5">
                        AI-powered talent matching engine
                      </p>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </UContainer>
    </section>

    <!-- ── MORE COMING SOON – Dark Section ───────────────────── -->
    <section class="relative overflow-hidden bg-slate-900">
      <div
        class="absolute inset-0 opacity-10"
        style="background-image: radial-gradient(circle, rgb(255 255 255 / 0.5) 1px, transparent 1px); background-size: 36px 36px;"
      />
      <div class="absolute -top-40 -left-40 w-[600px] h-[600px] rounded-full bg-primary/20 blur-[120px] pointer-events-none" />
      <div class="absolute -bottom-40 -right-40 w-[500px] h-[500px] rounded-full bg-indigo-600/20 blur-[120px] pointer-events-none" />

      <UContainer class="relative py-24">
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 lg:gap-20 items-center">
          <!-- Left -->
          <div class="scroll-reveal">
            <p class="text-sm font-semibold text-primary tracking-widest uppercase mb-4">
              What's Next
            </p>
            <h2 class="text-3xl md:text-4xl lg:text-5xl font-bold text-white leading-snug mb-6">
              More products are on the way.
              <span class="font-light text-white/60"> Stay tuned.</span>
            </h2>
            <p class="text-white/60 text-lg leading-relaxed">
              Yopaat continuously invests in building innovative technology products. Each one
              is grounded in real industry challenges and engineered to deliver measurable value.
            </p>
          </div>

          <!-- Right: placeholder cards -->
          <div class="grid grid-cols-1 sm:grid-cols-2 gap-4 scroll-reveal animation-delay-200">
            <div
              v-for="n in 4"
              :key="n"
              class="rounded-2xl border border-white/10 bg-white/5 p-6 flex flex-col gap-3"
            >
              <div class="w-8 h-8 rounded-lg bg-white/10 flex items-center justify-center">
                <UIcon
                  name="i-lucide-package"
                  class="w-4 h-4 text-white/30"
                />
              </div>
              <div class="h-3 w-24 bg-white/10 rounded-full" />
              <div class="h-2 w-full bg-white/5 rounded-full" />
              <div class="h-2 w-3/4 bg-white/5 rounded-full" />
              <span class="text-xs text-white/30 font-medium mt-1">Coming soon</span>
            </div>
          </div>
        </div>
      </UContainer>
    </section>

    <!-- ── CTA BANNER ──────────────────────────────────────────── -->
    <section class="relative overflow-hidden">
      <div class="absolute inset-0 bg-linear-to-br from-slate-900 via-slate-800 to-slate-900" />
      <div
        class="absolute inset-0 opacity-10"
        style="background-image: radial-gradient(circle, rgb(255 255 255 / 0.6) 1px, transparent 1px); background-size: 36px 36px;"
      />
      <div class="absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 w-[600px] h-[300px] rounded-full bg-primary/20 blur-[100px] pointer-events-none" />

      <UContainer class="relative py-28">
        <div class="scroll-reveal max-w-xl">
          <h2 class="text-3xl sm:text-4xl font-bold text-white leading-snug mb-6">
            Want to know more
            <span class="font-light text-white/70"> about our products or services?</span>
          </h2>
          <div class="flex flex-wrap gap-4">
            <UButton
              to="/contact"
              size="lg"
              class="rounded-full px-8 font-semibold"
              trailing-icon="i-lucide-arrow-right"
            >
              Get in Touch
            </UButton>
            <UButton
              to="/services"
              size="lg"
              color="neutral"
              variant="outline"
              class="rounded-full px-8 font-semibold border-white/20 text-white hover:bg-white/10"
            >
              Our Services
            </UButton>
          </div>
        </div>
      </UContainer>
    </section>
  </div>
</template>
