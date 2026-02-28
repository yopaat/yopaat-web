<script setup lang="ts">
useSeoMeta({
  title: 'Project Services — Yopaat',
  description: 'Today\'s consultancy and technology provision services require in-depth knowledge of an organisation and its business, together with a perfect vision on its industry.'
})

const services = [
  {
    icon: 'i-lucide-git-branch',
    title: 'Planning',
    body: 'Yopaat\'s planning services help see and benefit from what was not readily obvious and straight-forward. The differentiator between success and failure is in attention to detail. The expertise applied helps articulate plans geared for agile ways of working and related methodologies. Mapping business value over time-lines into programme activities is at the heart of Yopaat\'s planning services.'
  },
  {
    icon: 'i-lucide-rocket',
    title: 'Implementation',
    body: 'The depth and breadth of Yopaat\'s implementation services is vast, ranging from establishment of a blockchain-based music licensing platform for a publisher to a distributed system of street surveillance for a police force. Yopaat implements processes and technological enablers in an integral fashion in order to achieve the desired business outcomes in measurable and manageable ways.'
  },
  {
    icon: 'i-lucide-wrench',
    title: 'Maintenance, Support & Training',
    body: 'Yopaat\'s maintenance, support and training services extend a wide range from running a technological setting and continuously improving business processes to infrastructure and end-user support services. Proactive maintenance of ongoing functionality is not only attained by placing the right specialist on the projects but also by implementing the right sets of workflows and tool-sets.'
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
    <!-- ── HERO ─────────────────────────────────────────────── -->
    <section class="relative py-24 overflow-hidden">
      <div class="absolute inset-0 pointer-events-none">
        <div class="absolute top-0 left-1/4 w-[500px] h-[500px] rounded-full bg-primary/8 blur-[130px] animate-slow-pulse" />
        <div class="absolute bottom-0 right-1/4 w-[400px] h-[400px] rounded-full bg-indigo-500/8 blur-[110px] animate-slow-pulse animation-delay-1000" />
        <div
          class="absolute inset-0 opacity-20"
          style="background-image: radial-gradient(circle, rgb(148 163 184 / 0.4) 1px, transparent 1px); background-size: 36px 36px;"
        />
      </div>

      <UContainer class="relative text-center">
        <div class="flex items-center justify-center gap-2 text-sm text-muted mb-8 animate-fade-in">
          <NuxtLink
            to="/services"
            class="hover:text-foreground transition-colors"
          >Services</NuxtLink>
          <UIcon
            name="i-lucide-chevron-right"
            class="w-3 h-3"
          />
          <span>Project Services</span>
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

    <!-- ── SERVICE CARDS ──────────────────────────────────────── -->
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

    <!-- ── CTA BANNER ─────────────────────────────────────────── -->
    <section class="relative overflow-hidden">
      <div class="absolute inset-0 bg-gradient-to-br from-slate-900 via-slate-800 to-slate-900" />
      <div
        class="absolute inset-0 opacity-10"
        style="background-image: radial-gradient(circle, rgb(255 255 255 / 0.6) 1px, transparent 1px); background-size: 36px 36px;"
      />
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
