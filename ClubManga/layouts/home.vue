<!-- layouts/home.vue -->
<template>
  <div>
    <nav :class="['fixed top-0 left-0 right-0 bg-[#FB6F92] z-50 transition-transform duration-300', { '-translate-y-full': !showNavbar }]">
      <!-- Barre de navigation -->
      <div class="container mx-auto px-4 py-4 flex justify-between items-center">
        <NuxtLink to="/"><div class="text-xl text-[#FFC2D4]">Club Manga Dhuoda</div></NuxtLink>
        <ul class="hidden sm:flex space-x-6">
          <li><NuxtLink to="#home" class="text-[#FFEBF1] hover:text-[#FFC2D4] transition duration-300">Accueil</NuxtLink></li>
          <li><NuxtLink to="#presentation" class="text-[#FFEBF1] hover:text-[#FFC2D4] transition duration-300">Présentation</NuxtLink></li>
          <li><NuxtLink to="#projects" class="text-[#FFEBF1] hover:text-[#FFC2D4] transition duration-300">Projets</NuxtLink></li>
          <li><NuxtLink to="#Journee" class="text-[#FFEBF1] hover:text-[#FFC2D4] transition duration-300">Journée Japon</NuxtLink></li>
        </ul>
      </div>
    </nav>

    <!-- Contenu des sections -->
    <NuxtPage />

    <footer id="footer" class="bg-[#FFD6E0] py-8 text-center">
      <p class="text-sm">&copy; 2024 Site Club Manga Dhuoda.</p>
    </footer>
  </div>
</template>

<script>
export default {
  data() {
    return {
      showNavbar: true,
      lastScrollPosition: 0
    };
  },
  mounted() {
    this.lastScrollPosition = window.pageYOffset;
    window.addEventListener('scroll', this.onScroll);
  },
  beforeDestroy() {
    window.removeEventListener('scroll', this.onScroll);
  },
  methods: {
    onScroll() {
      const currentScrollPosition = window.pageYOffset;
      this.showNavbar = currentScrollPosition < this.lastScrollPosition || currentScrollPosition <= 100;
      this.lastScrollPosition = currentScrollPosition;
    }
  }
};
</script>

<style scoped>
/* Styles spécifiques pour le layout */
</style>
