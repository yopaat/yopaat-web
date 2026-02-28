<script setup lang="ts">
useSeoMeta({
  title: 'Consultancy Services — Yopaat',
  description: 'Today\'s consultancy and technology provision services require in-depth knowledge of an organisation and its business, together with a perfect vision on its industry.'
})

const services = [
  {
    icon: 'i-lucide-crown',
    title: 'Strategy Development',
    body: 'Thanks to years of experience in strategy and vision development, Yopaat offers extensive services in building corporate and programme strategy aligned with the past, present and the future of an organisation and its industry. Yopaat has extensive experience in building strategic roadmaps to help organizations to redefine their identity and their stance with regards to ongoing disruption possibilities.'
  },
  {
    icon: 'i-lucide-trending-up',
    title: 'Pre-Sales',
    body: 'Yopaat established itself as an expert provider of pre-sales services for its clients in the technology industry. Just to mention a few, Yopaat helped a client developing networking software solutions to define their product portfolio in tangible business terms in order to make the portfolio market-ready. Another case is where Yopaat helped an edge-computing technology developer to articulate their solution set in simple terms in order to express their solution sets in simple, business terms.'
  },
  {
    icon: 'i-lucide-cpu',
    title: 'Technology Architecture & Best Practices',
    body: 'Industry- and technology-specific best practices, reference architecture and specific architectures have long been parts of Yopaat\'s main capabilities. By utilizing proven sets of models and standards and by customizing those per clients\' priorities and needs, Yopaat delivers crucial foundational grounds for major corporate programmes and transformational efforts.'
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
    <!-- ── HERO ─────────────────────────────────────────── -->
    <section class="relative py-24 overflow-hidden">
      <!-- background blobs -->
      <div class="absolute inset-0 pointer-events-none">
        <div class="absolute top-0 left-1/4 w-[500px] h-[500px] rounded-full bg-primary/8 blur-[130px] animate-slow-pulse" />
        <div class="absolute bottom-0 right-1/4 w-[400px] h-[400px] rounded-full bg-indigo-500/8 blur-[110px] animate-slow-pulse animation-delay-1000" />
        <div
          class="absolute inset-0 opacity-20"
          style="background-image: radial-gradient(circle, rgb(148 163 184 / 0.4) 1px, transparent 1px); background-size: 36px 36px;"
        />
      </div>

      <UContainer class="relative text-center">
        <!-- breadcrumb -->
        <div class="flex items-center justify-center gap-2 text-sm text-muted mb-8 animate-fade-in">
          <NuxtLink
            to="/services"
            class="hover:text-foreground transition-colors"
          >
            Services
          </NuxtLink>
          <UIcon
            name="i-lucide-chevron-right"
            class="w-3 h-3"
          />
          <span>Consultancy Services</span>
        </div>

        <div class="animate-fade-in-up">
          <p class="text-xs font-semibold text-muted tracking-[0.25em] uppercase mb-5">
            Your Projects & Assignments in Safe Hands
          </p>
          <h1 class="text-4xl sm:text-5xl md:text-6xl font-bold leading-[1.15] mb-6 max-w-3xl mx-auto">
            <span class="font-light">Yopaat is here</span> to help you manage
            <span class="font-light"> that storm of change.</span>
          </h1>
          <p class="text-lg md:text-xl text-muted font-light leading-relaxed max-w-2xl mx-auto">
            Today's consultancy and technology provision services require in-depth knowledge of
            an organisation and its business, together with a perfect vision on the internal and
            external factors that dynamically impact an industry.
          </p>
        </div>
      </UContainer>
    </section>

    <!-- ── SERVICE CARDS ──────────────────────────────────── -->
    <section class="pb-24">
      <UContainer>
        <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
          <div
            v-for="(service, i) in services"
            :key="service.title"
            class="scroll-reveal"
            :style="`transition-delay: ${i * 0.15}s`"
          >
            <div
              class="h-full rounded-2xl border border-default bg-default p-8 flex flex-col gap-5
                        hover:border-primary/40 hover:shadow-xl hover:shadow-primary/10
                        hover:-translate-y-2 transition-all duration-300"
            >
              <!-- icon -->
              <div class="w-14 h-14 rounded-xl bg-primary/10 flex items-center justify-center shrink-0">
                <UIcon
                  :name="service.icon"
                  class="w-7 h-7 text-primary"
                />
              </div>

              <h2 class="text-xl font-bold leading-snug">
                {{ service.title }}
              </h2>

              <p class="text-muted text-sm leading-relaxed flex-1">
                {{ service.body }}
              </p>
            </div>
          </div>
        </div>
      </UContainer>
    </section>

    <!-- ── CTA BANNER ─────────────────────────────────────── -->
    <section class="relative overflow-hidden">
      <!-- dark gradient background -->
      <div class="absolute inset-0 bg-gradient-to-br from-slate-900 via-slate-800 to-slate-900" />
      <!-- subtle grid -->
      <div
        class="absolute inset-0 opacity-10"
        style="background-image: radial-gradient(circle, rgb(255 255 255 / 0.6) 1px, transparent 1px); background-size: 36px 36px;"
      />
      <!-- glow -->
      <div class="absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 w-[600px] h-[300px] rounded-full bg-primary/20 blur-[100px] pointer-events-none" />

      <UContainer class="relative py-28">
        <div class="scroll-reveal max-w-xl">
          <h2 class="text-3xl sm:text-4xl font-bold text-white leading-snug mb-6">
            Get in touch
            <span class="font-light text-white/70"> and let us know how we can help</span>
          </h2>
          <UButton
            to="/contact"
            size="lg"
            class="rounded-full px-8 font-semibold"
            trailing-icon="i-lucide-arrow-right"
          >
            Get Started
          </UButton>
        </div>
      </UContainer>
    </section>
  </div>
</template>
