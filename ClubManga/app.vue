<template>
    <nav class="fixed top-0 left-0 right-0 bg-[#FB6F92] z-50">
      <div class="container mx-auto px-4 py-4 flex justify-between items-center">
        <div class="text-xl text-[#FFC2D4]">Logo à venir</div>
        <ul class="hidden sm:flex space-x-6">
          <li><a href="#home" class="text-[#FFEBF1] hover:text-[#FFC2D4] transition duration-300">Accueil</a></li>
          <li><a href="#presentation" class="text-[#FFEBF1] hover:text-[#FFC2D4] transition duration-300">Présentation</a></li>
          <li><a href="#projects" class="text-[#FFEBF1] hover:text-[#FFC2D4] transition duration-300">Projets</a></li>
          <li><a href="#activities" class="text-[#FFEBF1] hover:text-[#FFC2D4] transition duration-300">Activités</a></li>
          <li><a href="#members" class="text-[#FFEBF1] hover:text-[#FFC2D4] transition duration-300">Membres</a></li>
        </ul>

        <div class="sm:hidden">
          <button @click="toggleMenu" class="text-[#FFEBF1]">
            <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" viewBox="0 0 24 24" stroke="currentColor">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
            </svg>
          </button>
        </div>
      </div>

      <ul v-if="isMenuOpen" class="sm:hidden bg-[#FB6F92] py-4 px-2">
        <li class="py-2"><a href="#home" class="block text-[#FFEBF1] hover:text-[#FFC2D4] transition duration-300">Accueil</a></li>
        <li class="py-2"><a href="#presentation" class="block text-[#FFEBF1] hover:text-[#FFC2D4] transition duration-300">Présentation</a></li>
        <li class="py-2"><a href="#projects" class="block text-[#FFEBF1] hover:text-[#FFC2D4] transition duration-300">Projets</a></li>
        <li class="py-2"><a href="#activities" class="block text-[#FFEBF1] hover:text-[#FFC2D4] transition duration-300">Activités</a></li>
        <li class="py-2"><a href="#members" class="block text-[#FFEBF1] hover:text-[#FFC2D4] transition duration-300">Membres</a></li>
      </ul>
    </nav>

  <div>
    <section id="home" class=" items-center justify-center flex min-h-screen bg-[#FFEBF1] px-4 sm:px-0">
      <div class="text-center">
        <h1 class="text-4xl sm:text-7xl text-[#13000A] text-center border-solid border-4 border-[#FB6F92] rounded-lg px-2 py-5">Club  Manga <br> Lycée  Dhuoda</h1>
      </div>
    </section>

    <section id="presentation" class="min-h-screen bg-[#FFC2D1] text-[#13000A] flex items-center justify-center">
      <div class="text-center">
        <h2 class="text-3xl mb-4">Présentation</h2>
        <p class="max-w-2xl">Nous sommes le club manga du lycée Dhuoda ...</p>
      </div>
    </section>

    <section id="projects" class="min-h-screen bg-[#FFEBF1] text-[#13000A] flex items-center justify-center">
      <div class="text-center">
        <h2 class="text-3xl mb-4">Projets</h2>
        <p class="max-w-2xl">à venir</p>
      </div>
    </section>


    <section id="members" class="min-h-screen bg-[#FFC2D1] text-[#13000A] flex items-center justify-center">
      <div class="text-center">
        <h2 class="text-3xl mb-4">Membres</h2>
        <p class="max-w-2xl">Présentation des différents membres.</p>
      </div>
    </section>

    <footer id="footer" class="bg-[#FFD6E0] text-[#13000A] py-8 text-center">
      <p class="text-sm sm:text-base">&copy; 2024 Site Club Manga Dhuoda. Réalisé par Téofane et Mohamany.</p>
    </footer>
  </div>

</template>

<script>
export default {
  name: 'HelloWorld',
  data() {
    return {
      isMenuOpen: false,
    };
  },
  methods: {
    toggleMenu() {
      this.isMenuOpen = !this.isMenuOpen;
    },
  },
}
</script>
