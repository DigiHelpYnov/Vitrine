<template>
  <footer class="bg-slate-900 text-slate-300">
    <div class="container mx-auto px-6 py-16">
      <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-12 mb-12">
        <div>
          <div class="flex items-center gap-3 mb-6">
            <div class="w-10 h-10 bg-gradient-to-br from-cyan-500 to-emerald-500 rounded-lg flex items-center justify-center">
              <Code2 :size="24" class="text-white" />
            </div>
            <span class="text-xl font-bold text-white">DevAgency</span>
          </div>
          <p class="text-slate-400 mb-6 leading-relaxed">
            Solutions digitales sur mesure pour transformer vos défis métiers en opportunités de croissance.
          </p>
          <div class="flex gap-4">
            <a
              href="https://linkedin.com"
              target="_blank"
              rel="noopener noreferrer"
              class="w-10 h-10 bg-slate-800 hover:bg-cyan-500 rounded-lg flex items-center justify-center transition-all duration-300"
            >
              <Linkedin :size="20" />
            </a>
            <a
              href="https://github.com"
              target="_blank"
              rel="noopener noreferrer"
              class="w-10 h-10 bg-slate-800 hover:bg-cyan-500 rounded-lg flex items-center justify-center transition-all duration-300"
            >
              <Github :size="20" />
            </a>
            <a
              href="https://twitter.com"
              target="_blank"
              rel="noopener noreferrer"
              class="w-10 h-10 bg-slate-800 hover:bg-cyan-500 rounded-lg flex items-center justify-center transition-all duration-300"
            >
              <Twitter :size="20" />
            </a>
          </div>
        </div>

        <div>
          <h3 class="text-white font-bold text-lg mb-6">Navigation</h3>
          <ul class="space-y-3">
            <li v-for="item in navigation" :key="item.id">
              <button
                @click="scrollToSection(item.id)"
                class="hover:text-cyan-400 transition-colors duration-200"
              >
                {{ item.label }}
              </button>
            </li>
          </ul>
        </div>

        <div>
          <h3 class="text-white font-bold text-lg mb-6">Services</h3>
          <ul class="space-y-3">
            <li v-for="service in services" :key="service" class="hover:text-cyan-400 transition-colors duration-200 cursor-pointer">
              {{ service }}
            </li>
          </ul>
        </div>

        <div>
          <h3 class="text-white font-bold text-lg mb-6">Contact</h3>
          <ul class="space-y-4">
            <li class="flex items-start gap-3">
              <Mail :size="20" class="text-cyan-400 flex-shrink-0 mt-0.5" />
              <a href="mailto:contact@agence-dev.fr" class="hover:text-cyan-400 transition-colors duration-200">
                contact@agence-dev.fr
              </a>
            </li>
            <li class="flex items-start gap-3">
              <Phone :size="20" class="text-cyan-400 flex-shrink-0 mt-0.5" />
              <a href="tel:+33123456789" class="hover:text-cyan-400 transition-colors duration-200">
                +33 1 23 45 67 89
              </a>
            </li>
          </ul>
          <button
            @click="scrollToSection('contact')"
            class="mt-6 w-full px-6 py-3 bg-gradient-to-r from-cyan-500 to-emerald-500 text-white rounded-lg font-semibold hover:shadow-lg hover:shadow-cyan-500/25 transition-all duration-300"
          >
            Obtenir un devis
          </button>
        </div>
      </div>

      <div class="border-t border-slate-800 pt-8">
        <div class="mb-8">
          <h4 class="text-white font-semibold mb-4">Technologies maîtrisées</h4>
          <div class="flex flex-wrap gap-2">
            <span
              v-for="(tech, index) in technologies"
              :key="index"
              class="px-3 py-1 bg-slate-800 text-slate-300 rounded-full text-sm hover:bg-slate-700 transition-colors duration-200"
            >
              {{ tech }}
            </span>
          </div>
        </div>

        <div class="flex flex-col md:flex-row justify-between items-center gap-4 text-sm text-slate-500">
          <p>
            {{ currentYear }} DevAgency. Tous droits réservés.
          </p>
          <div class="flex gap-6">
            <a href="#" class="hover:text-cyan-400 transition-colors duration-200">
              Mentions légales
            </a>
            <a href="#" class="hover:text-cyan-400 transition-colors duration-200">
              Politique de confidentialité
            </a>
            <a href="#" class="hover:text-cyan-400 transition-colors duration-200">
              CGV
            </a>
          </div>
        </div>
      </div>
    </div>
  </footer>
</template>

<script setup lang="ts">
import { Code2, Mail, Phone, Linkedin, Github, Twitter } from 'lucide-vue-next';

const currentYear = new Date().getFullYear();

const navigation = [
  { label: 'Accueil', id: 'hero' },
  { label: 'Solutions', id: 'solutions' },
  { label: 'Cas clients', id: 'case-studies' },
  { label: 'Process', id: 'process' },
  { label: 'Vision', id: 'vision' },
  { label: 'Contact', id: 'contact' }
];

const services = [
  'CRM personnalisés',
  'ERP internes',
  'Intégrations web',
  'Tableaux de bord',
  'Automatisations',
  'Applications web & mobile'
];

const technologies = [
  'React', 'TypeScript', 'Node.js', 'Python', 'PostgreSQL',
  'MongoDB', 'Docker', 'AWS', 'Next.js', 'Vue.js',
  'Tailwind CSS', 'Express', 'FastAPI', 'GraphQL', 'REST API'
];

const scrollToSection = (sectionId: string) => {
  document.getElementById(sectionId)?.scrollIntoView({ behavior: 'smooth' });
};
</script>

