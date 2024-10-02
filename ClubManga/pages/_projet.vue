<template>
  <div class="min-h-screen bg-[#FFEBF1] text-[#13000A] flex flex-col items-center justify-center">
    <h1 class="text-4xl mb-4">Projet : {{ projet }}</h1>
    <p class="max-w-2xl mx-auto text-gray-800 leading-relaxed text-lg md:text-xl">
      Voici la page dédiée au projet {{ projet }}. Ici, tu peux ajouter des détails spécifiques au projet en fonction du nom passé en paramètre.
    </p>
  </div>
</template>

<script setup>
import { useRoute } from 'vue-router'

const route = useRoute()
const projet = route.params.projet
</script>
