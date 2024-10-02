<template>
  <section id="projects" class="min-h-screen bg-[#FFEBF1] text-[#13000A] flex flex-col items-center justify-center">
    <!-- Ta section projets avec les nuxt-link -->
    <div class="relative w-full max-w-lg mx-auto">
      <div class="overflow-hidden">
        <nuxt-link
          v-for="(section, index) in Sections"
          :key="index"
          :to="{ name: 'projet', params: { projet: sectionNames[index] } }"
          class="block"
        >
          <img :src="section[0]" :alt="sectionNames[index]" class="w-full h-96 object-cover rounded-lg" />
          <p class="text-[#13000A] text-center text-lg mt-4">{{ sectionNames[index] }}</p>
        </nuxt-link>
      </div>

      <button @click="prevSection" class="absolute left-0 top-1/2 transform -translate-y-1/2 bg-gray-500/40 rounded-full hover:bg-gray-500/60 text-[#FFEBF1] transition-colors duration-300 px-4 py-2">
        <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" viewBox="0 0 24 24" stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M20 12H4M12 4l-8 8 8 8" fill="none"/>
        </svg>
      </button>

      <button @click="nextSection" class="absolute right-0 top-1/2 transform -translate-y-1/2 bg-gray-500/40 rounded-full hover:bg-gray-500/60 text-[#FFEBF1] transition-colors duration-300 px-4 py-2">
        <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" viewBox="0 0 24 24" stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 12h16M12 4l8 8-8 8" fill="none"/>
        </svg>
      </button>
    </div>
  </section>
</template>

<script>
import image1 from '~/assets/images/image1.jpg'
import image2 from '~/assets/images/image2.jpg'
import image3 from '~/assets/images/image3.jpg'
import image4 from '~/assets/images/image4.jpg'
import image5 from '~/assets/images/image5.jpg'
import peinture1 from '~/assets/images/peinture1.jpg'
import peinture2 from '~/assets/images/peinture2.jpg'
import peinture3 from '~/assets/images/peinture3.jpg'
import restaurant1 from '~/assets/images/restaurant1.jpg'
import one_shot from '~/assets/images/one_shot.jpg'

export default {
  data() {
    return {
      isMenuOpen: false,
      showNavbar: true,
      lastScrollPosition: 0,
      currentSectionIndex: 0,
      images: [image1, image2, image3, image4, image5],
      peinture: [peinture1, peinture2, peinture3],
      restaurant: [restaurant1],
      Concours_de_One_Shots: [one_shot],
      Sections: [], // Les sections pour chaque projet
      sectionNames: ['Peinture', 'Restaurant', 'Concours de One Shots'], // Les noms des projets
    };
  },
  created() {
    this.Sections = [this.peinture, this.restaurant, this.Concours_de_One_Shots];
  },
  methods: {
    nextSection() {
      this.currentSectionIndex = (this.currentSectionIndex + 1) % this.Sections.length;
    },
    prevSection() {
      this.currentSectionIndex = (this.currentSectionIndex - 1 + this.Sections.length) % this.Sections.length;
    },
  },
};
</script>
