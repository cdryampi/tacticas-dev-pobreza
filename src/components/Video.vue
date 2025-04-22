<script setup></script>
<template>
  <div
    class="relative min-h-screen flex items-center justify-center text-white overflow-hidden"
  >
    <!-- Video de fondo -->
    <video
      autoplay
      muted
      loop
      playsinline
      class="absolute w-full h-full object-cover"
    >
      <source src="../assets/ascetadev.mp4" type="video/mp4" />
      Tu navegador no soporta video HTML5.
    </video>

    <!-- Capa oscura semitransparente -->
    <div class="absolute inset-0 opacity-60 bg-black"></div>

    <!-- Contenido -->
    <div class="z-10 text-center px-4">
      <h1 class="text-4xl md:text-6xl font-bold">Desarrollo Web Para Pobres</h1>
      <blockquote class="text-lg mt-4 italic">
        Poca RAM, muchos sueños.
      </blockquote>
      <a
        href="#tacticas"
        class="mt-6 inline-block bg-white text-black px-6 py-3 rounded hover:bg-gray-200 transition"
      >
        $ npm install pobreza
      </a>
    </div>
  </div>
</template>
<style scoped></style>
