<template>
  <nav :class="['fixed top-0 left-0 right-0 bg-[#963852] z-50 transition-transform duration-300', { '-translate-y-full': !showNavbar }]">
    <div class="container mx-auto px-4 py-4 flex justify-between items-center">
      <NuxtLink to="/"><div class="text-xl text-[#FFC2D4]">Club Manga Dhuoda</div></NuxtLink>
      <ul class="hidden sm:flex space-x-6">
        <li><a href="#home" class="text-[#FFEBF1] hover:text-[#FFC2D4] transition duration-300">Accueil</a></li>
        <li>|</li>
        <li><a href="#presentation" class="text-[#FFEBF1] hover:text-[#FFC2D4] transition duration-300">Présentation</a></li>
        <li>|</li>
        <li><a href="#projects" class="text-[#FFEBF1] hover:text-[#FFC2D4] transition duration-300">Projets</a></li>
        <li>|</li>
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


    <section
  id="Journee"
  class="relative min-h-screen bg-[#FFC2D1] text-[#13000A] flex flex-col items-center justify-start bg-[url('assets/bg2.png')] bg-repeat"
  style="background-size: 6px 12px;"
>
  <div class="absolute top-0 left-0 w-full h-4 border-t-4 border-[#963852]"></div>

  <h2 class="text-4xl mt-4">Journée Japon</h2>

  <div class="flex justify-center gap-6 w-full max-w-5xl px-4 mt-10 relative">
    <!-- Case 1: Origami -->
    <div
      @click="handleClick('Origami')"
      :class="getCardClass('Origami')"
      class="flex-1 border-2 border-[#963852] rounded-sm p-4 relative cursor-pointer flex flex-col md:flex-row items-center justify-center"
    >
      <img
        :src="getIcon('Origami')"
        alt="Origami Icon"
        class="w-8 h-8 md:mr-2 mb-2 md:mb-0"
      />
      <h3 :class="{ 'text-white': selectedCard === 'Origami' }" class="text-xl text-center">Atelier Origami</h3>
      <div 
        v-if="selectedCard === 'Origami'" 
        class="absolute w-0 h-0 border-l-8 border-l-transparent border-r-8 border-r-transparent border-t-8 border-t-[#963852] bottom-[-8px] left-[calc(50%-8px)]" 
      ></div>
    </div>

    <!-- Case 2: Dessin -->
    <div
      @click="handleClick('Dessin')"
      :class="getCardClass('Dessin')"
      class="flex-1 border-2 border-[#963852] rounded-sm p-4 relative cursor-pointer flex flex-col md:flex-row items-center justify-center"
    >
      <img
        :src="getIcon('Dessin')"
        alt="Dessin Icon"
        class="w-8 h-8 md:mr-2 mb-2 md:mb-0"
      />
      <h3 :class="{ 'text-white': selectedCard === 'Dessin' }" class="text-xl text-center">Atelier Dessin</h3>
      <div 
        v-if="selectedCard === 'Dessin'" 
        class="absolute w-0 h-0 border-l-8 border-l-transparent border-r-8 border-r-transparent border-t-8 border-t-[#963852] bottom-[-8px] left-[calc(50%-8px)]" 
      ></div>
    </div>

    <!-- Case 3: Blind Test -->
    <div
      @click="handleClick('BlindTest')"
      :class="getCardClass('BlindTest')"
      class="flex-1 border-2 border-[#963852] rounded-sm p-4 relative cursor-pointer flex flex-col md:flex-row items-center justify-center"
    >
      <img
        :src="getIcon('BlindTest')"
        alt="Blind Test Icon"
        class="w-8 h-8 md:mr-2 mb-2 md:mb-0"
      />
      <h3 :class="{ 'text-white': selectedCard === 'BlindTest' }" class="text-xl text-center">Atelier Blindtest</h3>
      <div 
        v-if="selectedCard === 'BlindTest'" 
        class="absolute w-0 h-0 border-l-8 border-l-transparent border-r-8 border-r-transparent border-t-8 border-t-[#963852] bottom-[-8px] left-[calc(50%-8px)]" 
      ></div>
    </div>
  </div>


  <!-- Petit carré blanc avec coins arrondis et bordure -->
  <div class="mt-6 w-full max-w-lg mx-auto bg-white bg-opacity-50 border-2 border-white border-opacity-75 rounded-lg p-4">
    <p class="text-black text-center text-lg">{{ displayedText }}</p>
  </div>

  <div class="absolute bottom-0 left-0 w-full h-4 border-b-4 border-[#963852]"></div>
</section>





    <footer id="footer" class="bg-[#963852] text-[#ffebf1] py-8 text-center">
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
import origamiIcon from '@/assets/origami.png';
import origamiIconSelected from '@/assets/origami-b.png';
import dessinIcon from '@/assets/dessin.png';
import dessinIconSelected from '@/assets/dessin-b.png';
import blindtestIcon from '@/assets/blindtest.png';
import blindtestIconSelected from '@/assets/blindtest-b.png';

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
      selectedCard: 'Origami', // Par défaut, la première case est sélectionnée
      displayedText: `L'atelier origami sera organisé par Yanis Thomas et THEAUPHANEUH, les origami c'est cool HARRAY. Vous pourre venir participer, venez comme vous êtes tutududutu`, // Texte affiché par défaut
      icons: {
        Origami: {
          default: origamiIcon,
          selected: origamiIconSelected,
        },
        Dessin: {
          default: dessinIcon,
          selected: dessinIconSelected,
        },
        BlindTest: {
          default: blindtestIcon,
          selected: blindtestIconSelected,
        }
      },
      selectedCard: 'Origami',
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
    toggleEasteregg() {
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
    handleClick(card) {
      this.selectedCard = card;
      // Met à jour le texte affiché selon la case sélectionnée
      if (card === 'Origami') {
        this.displayedText = `L'atelier origami sera organisé par Yanis Thomas et THEAUPHANEUH, les origami c'est cool HARRAY. Vous pourre venir participer, venez comme vous êtes tutududutu`;
      } else if (card === 'Dessin') {
        this.displayedText = 'Dessin';
      } else if (card === 'BlindTest') {
        this.displayedText = 'Blind Test';
      }
    },
    getCardClass(card) {
      return {
        'bg-[#963852] text-white': this.selectedCard === card, // Change couleur de la case sélectionnée
        'bg-white text-black hover:text-[#963852]': this.selectedCard !== card, // Couleur par défaut avec hover
      };
    },
    getIcon(card) {
    if (this.selectedCard === card) {
      return this.icons[card].selected; // Icône en blanc pour la sélection
    }
    return this.icons[card].default; // Icône par défaut
  }
  },
};
</script>
