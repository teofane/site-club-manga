<template>
  <div class="container mx-auto text-center">
    <h1 class="text-4xl font-bold my-8">Bienvenue sur le site du Club Manga</h1>
    <p class="mb-4">Explorez nos projets passionnants :</p>
    <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
      <nuxt-link to="/peinture">
        <div class="border rounded-lg p-4 hover:bg-gray-100 transition duration-200">
          <img src="image-peinture.jpg" alt="Peinture" class="w-full h-48 object-cover mb-2" />
          <h2 class="text-2xl">Peinture</h2>
        </div>
      </nuxt-link>
      <nuxt-link to="/restaurant">
        <div class="border rounded-lg p-4 hover:bg-gray-100 transition duration-200">
          <img src="image-restaurant.jpg" alt="Restaurant" class="w-full h-48 object-cover mb-2" />
          <h2 class="text-2xl">Restaurant</h2>
        </div>
      </nuxt-link>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HomePage'
}
</script>

<style scoped>
/* Styles spécifiques à la page d'accueil */
.container {
  padding: 20px;
}
</style>
