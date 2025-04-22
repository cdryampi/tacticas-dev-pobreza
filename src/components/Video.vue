<script setup>
import { ref, onMounted } from "vue";
const moveArrow = () => {
  // Función que mueve la flecha hacia abajo hacia la primera sección
  const sections = document.getElementsByTagName("section");
  if (sections.length > 0) {
    sections[0].scrollIntoView({ behavior: "smooth" });
  }
};
</script>
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
      <div class="absolute bottom-1/5 left-1/2 transform -translate-x-1/2">
        <button
          @click="moveArrow"
          class="bg-white text-black rounded-full p-2 shadow-lg hover:bg-gray-200 transition cursor-pointer animate-bounce"
        >
          <svg
            xmlns="http://www.w3.org/2000/svg"
            class="h-6 w-6"
            fill="none"
            viewBox="0 0 24 24"
            stroke="currentColor"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M12 4v16m0 0l4-4m-4 4l-4-4"
            />
          </svg>
        </button>
      </div>
    </div>
  </div>
</template>
<style scoped></style>
