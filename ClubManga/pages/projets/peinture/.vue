<template>
  <section class="min-h-screen bg-[#FFC2D1] text-[#13000A] flex flex-col items-center justify-center">
    <h1 class="text-4xl mb-6">Peinture</h1>
    <p class="max-w-2xl mx-auto mb-4 p-4 text-lg md:text-xl text-center">
      Découvrez les différentes œuvres réalisées dans le cadre du projet Peinture. Chaque élève exprime sa créativité à travers des œuvres inspirées de l'univers manga.
    </p>
    <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
      <img v-for="(image, index) in peinture" :key="index" :src="image" :alt="'Peinture ' + (index + 1)" class="w-full h-64 object-cover rounded-lg shadow-md"/>
    </div>
  </section>
</template>

<script>
import peinture1 from '@/assets/peinture1.jpg';
import peinture2 from '@/assets/peinture2.jpg';
import peinture3 from '@/assets/peinture3.jpg';

export default {
  data() {
    return {
      peinture: [peinture1, peinture2, peinture3],
    };
  },
};
</script>

<style scoped>
  h1 {
    color: #13000A;
  }
</style>
