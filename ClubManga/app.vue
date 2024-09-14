<template>

  <nav class="fixed top-0 left-0 right-0 bg-[#FB6F92] z-50">
    <div class="container mx-auto px-4 py-4 flex justify-between items-center">
      <div class="text-xl text-[#FFC2D4]">Logo à venir</div>
      <ul class="flex space-x-6">
        <li><a href="#home" class="text-[#FFEBF1] hover:text-[#FFC2D4] transition duration-300">Accueil</a></li>
        <li><a href="#presentation" class="text-[#FFEBF1] hover:text-[#FFC2D4] transition duration-300">Présentation</a></li>
        <li><a href="#projects" class="text-[#FFEBF1] hover:text-[#FFC2D4] transition duration-300">Projets</a></li>
        <li><a href="#activities" class="text-[#FFEBF1] hover:text-[#FFC2D4] transition duration-300">Activités</a></li>
        <li><a href="#members" class="text-[#FFEBF1] hover:text-[#FFC2D4] transition duration-300">Membres</a></li>
      </ul>
    </div>
  </nav>

  <div>
    <section id="home" class=" items-center justify-center flex min-h-screen bg-[#FFEBF1]">
      <div class="text-center">
        <h1 class="text-7xl text-[#13000A] text-center border-solid border-4 border-[#FB6F92] rounded-lg px-2 py-5">Club  Manga <br> Lycée  Dhuoda</h1>
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
      <p>&copy; 2024 Site Club Manga Dhuoda. Réalisé par Téofane et Mohamany.</p>
    </footer>
  </div>

</template>

<script>
export default {
  name: 'HelloWorld'
}
</script>
