<template>
  <div class="min-h-screen bg-[#FFC2D1] text-[#13000A] flex flex-col items-center justify-center">
    <h1 class="text-4xl mb-6">Nos Projets</h1>
    <p class="max-w-2xl mx-auto mb-4 p-4 text-lg md:text-xl text-center">
      Explorez les différents projets réalisés par nos membres, allant de la peinture à la cuisine japonaise, en passant par des concours de création.
    </p>
    <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
      <nuxt-link to="/projets/peinture" class="flex flex-col items-center">
        <img src="~/assets/peinture-thumbnail.jpg" alt="Peinture" class="w-full h-64 object-cover rounded-lg shadow-md"/>
        <h2 class="mt-2 text-lg font-semibold">Peinture</h2>
      </nuxt-link>
      <nuxt-link to="/projets/restaurant" class="flex flex-col items-center">
        <img src="~/assets/restaurant-thumbnail.jpg" alt="Restaurant" class="w-full h-64 object-cover rounded-lg shadow-md"/>
        <h2 class="mt-2 text-lg font-semibold">Restaurant</h2>
      </nuxt-link>
      <nuxt-link to="/projets/concours-one-shot" class="flex flex-col items-center">
        <img src="~/assets/one-shot-thumbnail.jpg" alt="Concours de One Shots" class="w-full h-64 object-cover rounded-lg shadow-md"/>
        <h2 class="mt-2 text-lg font-semibold">Concours de One Shots</h2>
      </nuxt-link>
    </div>
  </div>
</template>

<style scoped>
h1 {
  color: #13000A;
}
</style>
