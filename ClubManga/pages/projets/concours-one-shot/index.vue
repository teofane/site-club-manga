<template>
  <section class="min-h-screen bg-[#FFC2D1] text-[#13000A] flex flex-col items-center justify-center">
    <h1 class="text-4xl mb-6">Concours de One Shots</h1>
    <p class="max-w-2xl mx-auto mb-4 p-4 text-lg md:text-xl text-center">
      Participez à notre concours de One Shots ! Présentez vos œuvres courtes et laissez libre cours à votre imagination dans ce format unique.
    </p>
    <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
      <img :src="oneShot" alt="Concours de One Shot" class="w-full h-64 object-cover rounded-lg shadow-md"/>
    </div>
  </section>
</template>

<script>
import oneShot from '@/assets/one-shot.jpg';

export default {
  data() {
    return {
      oneShot,
    };
  },
};
</script>

<style scoped>
  h1 {
    color: #13000A;
  }
</style>
