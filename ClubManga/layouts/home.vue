<!-- layouts/home.vue -->
<template>
  <div>
    <nav :class="['fixed top-0 left-0 right-0 bg-[#FB6F92] z-50 transition-transform duration-300', { '-translate-y-full': !showNavbar }]">
      <!-- Barre de navigation -->
    </nav>

    <!-- Contenu des sections -->
    <section id="home" class="items-center justify-center flex min-h-screen bg-[#FFEBF1] px-4 sm:px-0">
      <!-- Section d'accueil -->
    </section>
    <section id="presentation" class="min-h-screen bg-[#FFC2D1]">
      <!-- Présentation -->
    </section>
    <section id="projects" class="min-h-screen bg-[#FFEBF1]">
      <!-- Projets -->
    </section>
    <section id="Journee" class="min-h-screen bg-[#FFC2D1]">
      <!-- Journée Japon -->
    </section>
    <footer id="footer" class="bg-[#FFD6E0] py-8 text-center">
      <!-- Footer -->
    </footer>
  </div>
</template>
