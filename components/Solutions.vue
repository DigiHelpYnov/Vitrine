<template>
  <section id="solutions" class="py-24 bg-slate-50">
    <div class="container mx-auto px-6">
      <div class="text-center mb-16">
        <h2 class="text-4xl md:text-5xl font-bold text-slate-900 mb-4">
          Nos Solutions
        </h2>
        <p class="text-xl text-slate-600 max-w-2xl mx-auto">
          Des outils digitaux conçus pour répondre précisément à vos enjeux métiers
        </p>
      </div>

      <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8 max-w-7xl mx-auto">
        <div
          v-for="(solution, index) in solutions"
          :key="index"
          class="group bg-white rounded-2xl p-8 shadow-lg hover:shadow-2xl transition-all duration-300 border border-slate-100 hover:border-cyan-200 hover:-translate-y-1"
        >
          <div :class="['w-14 h-14 rounded-xl bg-gradient-to-br flex items-center justify-center mb-6 group-hover:scale-110 transition-transform duration-300', solution.color]">
            <component :is="solution.icon" :size="28" class="text-white" />
          </div>

          <h3 class="text-2xl font-bold text-slate-900 mb-3">
            {{ solution.title }}
          </h3>

          <p class="text-slate-600 leading-relaxed">
            {{ solution.description }}
          </p>
        </div>
      </div>

      <div class="text-center mt-16">
        <button
          @click="scrollToContact"
          class="px-8 py-4 bg-gradient-to-r from-cyan-500 to-emerald-500 text-white rounded-lg font-semibold text-lg hover:shadow-xl hover:shadow-cyan-500/25 transition-all duration-300"
        >
          Discutons de votre projet
        </button>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { Database, Workflow, Layers, BarChart3, Zap, Smartphone } from 'lucide-vue-next';

const solutions = [
  {
    icon: Database,
    title: 'CRM personnalisés',
    description: 'Gérez vos relations clients avec des outils adaptés à vos processus métiers et vos besoins spécifiques.',
    color: 'from-cyan-500 to-blue-500'
  },
  {
    icon: Layers,
    title: 'ERP internes',
    description: 'Centralisez la gestion de votre entreprise : stocks, comptabilité, RH, et bien plus encore.',
    color: 'from-emerald-500 to-teal-500'
  },
  {
    icon: Workflow,
    title: 'Intégrations web',
    description: 'Connectez vos systèmes existants via des API robustes et des architectures front/back sur mesure.',
    color: 'from-purple-500 to-pink-500'
  },
  {
    icon: BarChart3,
    title: 'Tableaux de bord & outils de gestion',
    description: 'Visualisez vos données en temps réel avec des dashboards intuitifs et performants.',
    color: 'from-orange-500 to-red-500'
  },
  {
    icon: Zap,
    title: 'Automatisations',
    description: 'Éliminez les tâches répétitives et gagnez du temps avec des workflows automatisés intelligents.',
    color: 'from-yellow-500 to-orange-500'
  },
  {
    icon: Smartphone,
    title: 'Applications web et mobiles',
    description: 'Développement d\'applications performantes pour tous les supports, adaptées à votre activité.',
    color: 'from-indigo-500 to-blue-500'
  }
];

const scrollToContact = () => {
  document.getElementById('contact')?.scrollIntoView({ behavior: 'smooth' });
};
</script>

