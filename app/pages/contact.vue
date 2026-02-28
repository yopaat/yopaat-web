<script setup lang="ts">
import type { FormError, FormSubmitEvent } from '#ui/types'

useSeoMeta({
  title: 'Contact — Yopaat',
  description: 'Get in touch with Yopaat. Whether you need consultancy, project services, or simply want to explore how we can help — we would love to hear from you.'
})

const state = reactive({
  name: '',
  email: '',
  message: ''
})

type Schema = typeof state

const toast = useToast()
const submitted = ref(false)

function validate(state: Partial<Schema>): FormError[] {
  const errors: FormError[] = []
  if (!state.name?.trim()) errors.push({ name: 'name', message: 'Your name is required.' })
  if (!state.email?.trim()) {
    errors.push({ name: 'email', message: 'Your email is required.' })
  } else if (!/^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(state.email)) {
    errors.push({ name: 'email', message: 'Please enter a valid email address.' })
  }
  if (!state.message?.trim()) errors.push({ name: 'message', message: 'Please write a message.' })
  return errors
}

async function onSubmit(_event: FormSubmitEvent<Schema>) {
  // TODO: wire up to a real API endpoint
  await new Promise(resolve => setTimeout(resolve, 800))
  submitted.value = true
  toast.add({
    title: 'Message sent!',
    description: 'Thanks for reaching out. We\'ll get back to you shortly.',
    color: 'success',
    icon: 'i-lucide-check-circle'
  })
}

const contactItems = [
  { icon: 'i-lucide-mail', label: 'Email', value: 'info@yopaat.com', href: 'mailto:info@yopaat.com' },
  { icon: 'i-lucide-globe', label: 'Website', value: 'yopaat.com', href: 'https://yopaat.com' }
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
            <span class="font-light text-muted">Let's navigate</span><br>
            the storm
            <span class="text-transparent bg-clip-text bg-linear-to-r from-blue-500 to-indigo-600"> together.</span>
          </h1>
          <p class="text-lg md:text-xl text-muted font-light leading-relaxed max-w-2xl mx-auto">
            Whether you need consultancy, project delivery, or just want to explore how Yopaat
            can help — we'd love to hear from you.
          </p>
        </div>
      </UContainer>
    </section>

    <!-- ── CONTACT SECTION ───────────────────────────────────── -->
    <section class="pb-28">
      <UContainer>
        <div class="grid grid-cols-1 lg:grid-cols-5 gap-10 lg:gap-16">
          <!-- ── Left: Info panel ─────────────────────────────── -->
          <div class="lg:col-span-2 scroll-reveal">
            <div class="sticky top-28 flex flex-col gap-8">
              <!-- Info header -->
              <div>
                <p class="text-sm font-semibold text-primary tracking-widest uppercase mb-3">
                  Get in Touch
                </p>
                <h2 class="text-2xl md:text-3xl font-bold leading-snug mb-4">
                  Ready to start a conversation?
                </h2>
                <p class="text-muted leading-relaxed">
                  Fill in the form and one of our team members will respond within one business day.
                  We're here to help you find the right solution.
                </p>
              </div>

              <!-- Contact details -->
              <div class="flex flex-col gap-4">
                <a
                  v-for="item in contactItems"
                  :key="item.label"
                  :href="item.href"
                  target="_blank"
                  rel="noopener noreferrer"
                  class="group flex items-center gap-4 rounded-2xl border border-default bg-elevated p-5 hover:border-primary/30 hover:shadow-md transition-all duration-300"
                >
                  <div class="w-11 h-11 rounded-xl bg-primary/10 group-hover:bg-primary/20 flex items-center justify-center shrink-0 transition-colors duration-300">
                    <UIcon
                      :name="item.icon"
                      class="w-5 h-5 text-primary"
                    />
                  </div>
                  <div>
                    <p class="text-xs text-muted font-medium mb-0.5">{{ item.label }}</p>
                    <p class="font-semibold text-sm">{{ item.value }}</p>
                  </div>
                  <UIcon
                    name="i-lucide-arrow-up-right"
                    class="w-4 h-4 text-muted ml-auto opacity-0 group-hover:opacity-100 transition-opacity duration-200"
                  />
                </a>
              </div>

              <!-- Reassurance block (dark) -->
              <div class="relative rounded-2xl bg-slate-900 overflow-hidden p-6">
                <div
                  class="absolute inset-0 opacity-10"
                  style="background-image: radial-gradient(circle, rgb(255 255 255 / 0.4) 1px, transparent 1px); background-size: 24px 24px;"
                />
                <div class="absolute -top-10 -right-10 w-40 h-40 rounded-full bg-primary/20 blur-[60px] pointer-events-none" />
                <div class="relative">
                  <div class="w-10 h-10 rounded-xl bg-primary/20 flex items-center justify-center mb-4">
                    <UIcon
                      name="i-lucide-shield-check"
                      class="w-5 h-5 text-primary/80"
                    />
                  </div>
                  <p class="font-semibold text-white mb-1">
                    Your data is safe with us.
                  </p>
                  <p class="text-white/60 text-sm leading-relaxed">
                    We only use your information to respond to your inquiry and will never share it with third parties.
                  </p>
                </div>
              </div>
            </div>
          </div>

          <!-- ── Right: Form ──────────────────────────────────── -->
          <div class="lg:col-span-3 scroll-reveal animation-delay-200">
            <!-- Success state -->
            <Transition
              enter-active-class="transition-all duration-500"
              enter-from-class="opacity-0 translate-y-4"
              enter-to-class="opacity-100 translate-y-0"
            >
              <div
                v-if="submitted"
                class="rounded-3xl border border-emerald-500/30 bg-emerald-500/10 p-12 text-center"
              >
                <div class="w-16 h-16 rounded-full bg-emerald-500/20 flex items-center justify-center mx-auto mb-6">
                  <UIcon
                    name="i-lucide-check"
                    class="w-8 h-8 text-emerald-500"
                  />
                </div>
                <h3 class="text-2xl font-bold mb-3">
                  Message Sent!
                </h3>
                <p class="text-muted leading-relaxed mb-8 max-w-sm mx-auto">
                  Thank you for reaching out. We'll get back to you within one business day.
                </p>
                <UButton
                  variant="outline"
                  color="neutral"
                  class="rounded-full px-8"
                  @click="submitted = false; state.name = ''; state.email = ''; state.message = ''"
                >
                  Send another message
                </UButton>
              </div>
            </Transition>

            <!-- Form state -->
            <Transition
              enter-active-class="transition-all duration-500"
              enter-from-class="opacity-0 translate-y-4"
              enter-to-class="opacity-100 translate-y-0"
            >
              <div
                v-if="!submitted"
                class="rounded-3xl border border-default bg-elevated p-8 md:p-10 shadow-xl shadow-black/5"
              >
                <h3 class="text-xl font-bold mb-1">
                  Send us a message
                </h3>
                <p class="text-muted text-sm mb-8">
                  All fields are required.
                </p>

                <UForm
                  :validate="validate"
                  :state="state"
                  class="flex flex-col gap-6"
                  @submit="onSubmit"
                >
                  <!-- Name -->
                  <UFormField
                    label="Your Name"
                    name="name"
                    required
                  >
                    <UInput
                      v-model="state.name"
                      placeholder="Jane Doe"
                      size="lg"
                      class="w-full"
                      leading-icon="i-lucide-user"
                    />
                  </UFormField>

                  <!-- Email -->
                  <UFormField
                    label="Email Address"
                    name="email"
                    required
                  >
                    <UInput
                      v-model="state.email"
                      type="email"
                      placeholder="jane@company.com"
                      size="lg"
                      class="w-full"
                      leading-icon="i-lucide-mail"
                    />
                  </UFormField>

                  <!-- Message -->
                  <UFormField
                    label="Message"
                    name="message"
                    required
                  >
                    <UTextarea
                      v-model="state.message"
                      placeholder="Tell us about your project or how we can help..."
                      :rows="6"
                      size="lg"
                      class="w-full"
                      autoresize
                    />
                  </UFormField>

                  <!-- Submit -->
                  <UButton
                    type="submit"
                    size="lg"
                    class="rounded-full px-10 font-semibold w-full justify-center shadow-lg shadow-primary/20"
                    trailing-icon="i-lucide-send"
                  >
                    Send Message
                  </UButton>
                </UForm>
              </div>
            </Transition>
          </div>
        </div>
      </UContainer>
    </section>
  </div>
</template>
