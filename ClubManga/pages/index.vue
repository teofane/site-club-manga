<template>
  <div class="min-h-screen bg-[#FFC2D1] text-[#13000A] flex flex-col items-center justify-center">
    <h1 class="text-5xl font-bold mb-4">Bienvenue au Club Manga !</h1>
    <p class="max-w-2xl mx-auto mb-6 p-4 text-lg md:text-xl text-center">
      Rejoignez-nous pour explorer la culture manga à travers divers projets créatifs. Découvrez nos œuvres, participez à des concours et partagez votre passion avec d'autres amateurs.
    </p>
    <nuxt-link to="/projets" class="bg-[#13000A] text-white px-6 py-3 rounded-lg hover:bg-[#D7B5C3] transition duration-300">
      Explorer nos Projets
    </nuxt-link>
  </div>
</template>

<style scoped>
h1 {
  color: #13000A;
}
</style>


