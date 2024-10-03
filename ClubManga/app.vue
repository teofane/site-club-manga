<template>
  <nav :class="['fixed top-0 left-0 right-0 bg-[#FB6F92] z-50 transition-transform duration-300', { '-translate-y-full': !showNavbar }]">
    <div class="container mx-auto px-4 py-4 flex justify-between items-center">
      <NuxtLink to="/"><div class="text-xl text-[#FFC2D4]">Club Manga Dhuoda</div></NuxtLink>
      <ul class="hidden sm:flex space-x-6">
        <li><a href="#home" class="text-[#FFEBF1] hover:text-[#FFC2D4] transition duration-300">Accueil</a></li>
        <li><a href="#presentation" class="text-[#FFEBF1] hover:text-[#FFC2D4] transition duration-300">Présentation</a></li>
        <li><a href="#projects" class="text-[#FFEBF1] hover:text-[#FFC2D4] transition duration-300">Projets</a></li>
        <li><a href="#Journee" class="text-[#FFEBF1] hover:text-[#FFC2D4] transition duration-300">Journée Japon</a></li>
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
      <li class="py-2"><a href="#Journee" class="block text-[#FFEBF1] hover:text-[#FFC2D4] transition duration-300">Journée Japon</a></li>
    </ul>
  </nav>

  <div>
    <section id="home" class="items-center justify-center flex min-h-screen bg-[#FFEBF1] px-4 sm:px-0">
      <div class="text-center">
        <h1 class="text-4xl sm:text-7xl text-[#13000A] text-center border-solid border-4 border-[#FB6F92] rounded-lg px-2 py-5">Club Manga <br> Lycée Dhuoda</h1>
      </div>
    </section>

    <section id="presentation" class="min-h-screen bg-[#FFC2D1] text-[#13000A] flex flex-col items-center justify-center">
      <div class="text-center mb-4">
        <h2 class="text-3xl mb-4">Présentation</h2>
        <p class="max-w-2xl mx-auto p-4 text-gray-800 leading-relaxed text-lg md:text-xl">Le Club Manga du Lycée Dhuoda est un espace pour les passionnés de mangas, d'anime, de dessin et de culture japonaise. Que vous soyez amateur d'œuvres japonaises ou simplement curieux de découvrir les traditions et l'art du Japon, notre club vous invite à partager vos passions et à explorer ensemble l'univers fascinant de la culture nippone. Rejoignez-nous et plongez dans cet univers captivant !</p>
      </div>

      <div class="relative w-full max-w-lg mx-auto">
        <div class="overflow-hidden">
          <img v-for="(image, index) in images":key="index":src="image":alt="'Image ' + (index + 1)" v-show="currentIndex === index" class="w-full h-96 object-cover rounded-lg" />
        </div>
        <button @click="prevImage" class="absolute left-0 top-1/2 transform -translate-y-1/2 bg-gray-500/40 rounded-full hover:bg-gray-500/60 text-[#FFEBF1] transition-colors duration-300 px-4 py-2">
          <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M20 12H4M12 4l-8 8 8 8" fill="none"/>
          </svg>
        </button>
        <button @click="nextImage" class="absolute right-0 top-1/2 transform -translate-y-1/2 bg-gray-500/40 rounded-full hover:bg-gray-500/60 text-[#FFEBF1] transition-colors duration-300 px-4 py-2">
          <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 12h16M12 4l8 8-8 8" fill="none"/>
          </svg>
        </button>
      </div>
    </section>

    <section id="projects" class="min-h-screen bg-[#FFEBF1] text-[#13000A] flex flex-col items-center justify-center">
      <div class="text-center">
        <h2 class="text-3xl mb-4">Projets</h2>
        <p class="max-w-2xl mx-auto p-4 text-gray-800 leading-relaxed text-lg md:text-xl">Le club manga offre de nombreux projets :</p>
      </div>

      <div class="relative w-full max-w-lg mx-auto">
        <div class="overflow-hidden">
            <NuxtLink v-for="(section, index) in Sections" :key="index" :to="sectionRoutes[index]">
              <img :src="section[0]" v-show="currentSectionIndex === index" class="w-full h-96 object-cover rounded-lg" />
              <p v-show="currentSectionIndex === index" class="text-[#13000A] text-center text-lg mt-4">{{ sectionNames[index] }}</p>
            </NuxtLink>
          <NuxtPage />
        </div>
        
        <button @click="prevSection" class="absolute left-0 top-1/2 transform -translate-y-1/2 bg-gray-500/40 rounded-full hover:bg-gray-500/60 text-[#FFEBF1] transition-colors duration-300 px-4 py-2">
          <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M20 12H4M12 4l-8 8 8 8" fill="none" />
          </svg>
        </button>
        <button @click="nextSection" class="absolute right-0 top-1/2 transform -translate-y-1/2 bg-gray-500/40 rounded-full hover:bg-gray-500/60 text-[#FFEBF1] transition-colors duration-300 px-4 py-2">
          <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 12h16M12 4l8 8-8 8" fill="none" />
          </svg>
        </button>
      </div>
    </section>

    <section id="Journee" class="min-h-screen bg-[#FFC2D1] text-[#13000A] flex items-center justify-center">
      <div class="text-center">
        <h2 class="text-3xl mb-4">Journée japon</h2>
        <p class="max-w-2xl">Présentation de la journee</p>
      </div>
    </section>

    <footer id="footer" class="bg-[#FFD6E0] text-[#13000A] py-8 text-center">
      <p class="text-sm sm:text-base">&copy; 2024 Site Club Manga Dhuoda. Réalisé par <a @click="toogleEasteregg">Téofane</a> et Bilal.</p>
    </footer>

    <div v-if="isEastereggOpen" class="fixed inset-0 flex items-center justify-center bg-gray-800 bg-opacity-20 z-50">
      <div class="text-center">
        <svg @click="toogleEasteregg" xmlns="http://www.w3.org/2000/svg" width="70" height="70" viewBox="0 0 100 100" class="absolute top-0 sm:top-5 right-0 sm:right-[25%] opacity-75 color-[#13000A]">
          <rect x="45" y="10" width="10" height="80" fill="black" transform="rotate(45 50 50)"/>
          <rect x="10" y="45" width="80" height="10" fill="black" transform="rotate(45 50 50)"/>
        </svg>

        <img src="@/assets/SGSPTHTWMID4CLTODA4R.png" class="mb-4" alt="Easter Egg Image"/>
        <p class="text-[#FFEBF1] text-lg">Watashi no stando <a href="https://jjba.fandom.com/fr/wiki/Silver_Chariot" target="_blank" >Silver</a> <a href="https://jjba.fandom.com/fr/wiki/Gold_Experience" target="_blank">golden</a> <a href="https://jjba.fandom.com/fr/wiki/Star_Platinum" target="_blank">star platinium</a> <a href="https://jjba.fandom.com/fr/wiki/The_Hand" target="_blank">the hand</a> <a href="https://jjba.fandom.com/fr/wiki/The_World" target="_blank">the world</a> <a href="https://jjba.fandom.com/fr/wiki/Made_in_Heaven" target="_blank">made in</a> <a href="https://jjba.fandom.com/fr/wiki/Dirty_Deeds_Done_Dirt_Cheap" target="_blank">dirty deeds done dirt cheap</a> <a href="https://jojowiki.com/D4C_Love_Train/fr" target="_blank">love train</a> <a href="https://jjba.fandom.com/fr/wiki/The_World_Over_Heaven" target="_blank">overheaven</a><a href="https://jjba.fandom.com/fr/wiki/Heaven%27s_Door" target="_blank">'s door</a> <a href="https://jjba.fandom.com/fr/wiki/Tusk#Tusk_ACT4" target="_blank">act 4</a> <a href="https://jjba.fandom.com/fr/wiki/Gold_Experience_Requiem" target="_blank">requiem</a></p>
        </div>
    </div>

  </div>
</template>

<script>
import image1 from '@/assets/image1.jpg';
import image2 from '@/assets/image2.jpg';
import image3 from '@/assets/image3.jpg';
import image4 from '@/assets/image4.jpg';
import image5 from '@/assets/image5.jpg';
import peinture1 from '@/assets/peinture1.jpg';
import peinture2 from '@/assets/peinture2.jpg';
import peinture3 from '@/assets/peinture3.jpg';
import restaurant1 from '@/assets/restaurant.jpg';
import one_shot from '@/assets/one-shot.jpg';

export default {
  data() {
    return {
      isMenuOpen: false,
      showNavbar: true,
      lastScrollPosition: 0,
      isEastereggOpen: false,
      currentIndex: 0,
      images: [image1, image2, image3, image4, image5],
      peinture: [peinture1, peinture2, peinture3],
      restaurant: [restaurant1],
      Concours_de_One_Shots: [one_shot],
      currentSectionIndex: 0,
      Sections: [],
      sectionNames: ['Peinture', 'Restaurant', 'Concours de One Shots'],
      sectionRoutes: ['/projets/peinture', '/projets/restaurant', '/projets/concours-one-shot'],
    };
  },
  created() {
    this.Sections = [this.peinture, this.restaurant, this.Concours_de_One_Shots];
    this.currentSection = this.Sections[0];
  },
  mounted() {
    this.lastScrollPosition = window.pageYOffset;
    window.addEventListener('scroll', this.onScroll);
  },
  beforeDestroy() {
    window.removeEventListener('scroll', this.onScroll);
  },
  methods: {
    toggleMenu() {
      this.isMenuOpen = !this.isMenuOpen;
    },
    toogleEasteregg() {
      this.isEastereggOpen = !this.isEastereggOpen;
    },
    onScroll() {
      const currentScrollPosition = window.pageYOffset;

      if (currentScrollPosition > this.lastScrollPosition && currentScrollPosition > 100) {
        this.showNavbar = false;
      } else {
        this.showNavbar = true;
      }

      this.lastScrollPosition = currentScrollPosition;
    },
    nextImage() {
      this.currentIndex = (this.currentIndex + 1) % this.images.length;
    },
    prevImage() {
      this.currentIndex = (this.currentIndex - 1 + this.images.length) % this.images.length;
    },
    nextSection() {
    this.currentSectionIndex = (this.currentSectionIndex + 1) % this.Sections.length;
      },
        prevSection() {
          this.currentSectionIndex = (this.currentSectionIndex - 1 + this.Sections.length) % this.Sections.length;
      },
  },
};
</script>
