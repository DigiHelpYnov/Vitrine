<template>
  <div class="min-h-screen flex flex-col bg-white text-slate-900">
    <header class="fixed inset-x-0 top-0 z-50 bg-white/80 backdrop-blur border-b border-slate-200">
      <div class="container mx-auto px-6 py-4 flex items-center justify-between">
        <NuxtLink to="/" class="flex items-center gap-3 text-slate-900 font-semibold text-lg interactive-hover">
          <span class="inline-flex h-10 w-10 items-center justify-center rounded-lg bg-gradient-to-br from-cyan-500 to-emerald-500 text-white shadow-lg">
            DH
          </span>
          DigiHelp
        </NuxtLink>
        <nav class="flex items-center gap-6 text-sm font-medium">
          <NuxtLink
            v-for="link in links"
            :key="link.to"
            :to="link.to"
            class="relative transition-colors hover:text-cyan-600"
            active-class="text-cyan-600"
          >
            {{ link.label }}
          </NuxtLink>
        </nav>
      </div>
    </header>

    <main class="flex-1 pt-24">
      <slot />
    </main>

    <Footer />
  </div>
</template>

<script setup lang="ts">
import Footer from '~/components/Footer.vue';

const links = [
  { label: 'Accueil', to: '/' },
  { label: 'Offre', to: '/solutions' },
  { label: 'Contact', to: '/contact' }
];
</script>

