<script setup>
import { ref } from "vue";
import { mandamientoData } from "../data/mandamientoData.js";

const spinner = ref(false);

const mandamientoList = ref(mandamientoData.splice(0, 3));

const loadMore = () => {
  spinner.value = true;
  setTimeout(() => {
    spinner.value = false;
    updateMandamientoList();
  }, 1000);
};

const updateMandamientoList = () => {
  const newItems = mandamientoData.splice(0, 3);
  if (newItems.length > 0) {
    mandamientoList.value.push(...newItems);
  } else {
    console.log("No hay más elementos para cargar.");
  }
};
</script>
<template>
  <section class="container mx-auto p-4" id="roadmap">
    <h2
      class="text-3xl md:text-4xl lg:text-5xl font-bold text-gray-900 dark:text-white text-center mb-8 md:mb-16"
    >
      Mandamiento de los aspirantes a ascetadevs:
    </h2>
    <blockquote class="italic dark:text-gray-400 mb-12 text-center">
      “Cada crash, cada deploy fallido… nos acerca más a la iluminación backend
      sin presupuesto.”
    </blockquote>
    <div class="relative">
      <!-- Línea del roadmap (visible solo en pantallas grandes) -->
      <div
        class="hidden lg:block absolute left-1/2 transform -translate-x-1/2 w-1 bg-primary-950 h-full rounded-lg"
      ></div>

      <div
        v-for="(item, index) in mandamientoList"
        :key="item.id"
        class="flex flex-col md:flex-row items-center mb-6 relative group"
        :class="{ 'md:flex-row-reverse': index % 2 !== 0 }"
        :data-aos="'fade-' + (index % 2 === 0 ? 'right' : 'left')"
      >
        <!-- Círculo en la línea (solo en pantallas grandes) -->
        <div
          class="hidden lg:flex absolute left-1/2 transform -translate-x-1/2"
        >
          <div
            class="w-8 h-8 bg-primary-950 rounded-full flex items-center justify-center ring-8 ring-white dark:ring-gray-900"
          >
            <svg
              class="w-5 h-5 text-white"
              fill="currentColor"
              viewBox="0 0 24 24"
            >
              <path
                d="M18 8h1a3 3 0 1 1 0 6h-1v1a5 5 0 0 1-5 5H7a5 5 0 0 1-5-5V8h16Zm1 4a1 1 0 1 0 0-2h-1v2h1ZM6 20h11a1 1 0 1 1 0 2H6a1 1 0 1 1 0-2Z"
              />
            </svg>
          </div>
        </div>

        <!-- Contenedor del reto -->
        <a
          href="#"
          class="p-6 bg-white shadow-lg rounded-lg dark:bg-gray-800 transition-all hover:scale-105 w-full sm:w-3/4 md:w-1/2 lg:w-1/2"
          :class="{
            'md:ml-auto': index % 2 !== 0,
            'md:mr-auto': index % 2 === 0,
          }"
        >
          <h3
            class="text-lg font-semibold text-gray-900 dark:text-white flex items-center"
          >
            {{ item.title }}
          </h3>

          <small class="block mb-2 text-sm text-gray-400 dark:text-gray-500">
            {{ item.subtitle }}
          </small>

          <p class="text-base text-gray-500 dark:text-gray-400">
            {{ item.description }}
          </p>
        </a>
      </div>

      <!-- Botón para cargar más retos con spinner -->
      <div class="flex justify-center my-10 relative">
        <button
          type="button"
          @click="loadMore"
          v-if="!spinner && mandamientoData.length > 0"
          class="p-4 flex items-center rounded-full border border-primary-300 bg-primary-950 text-sm font-medium text-primary-100 hover:bg-primary-100 hover:text-primary-950 transition-all duration-300"
        >
          <svg class="mr-2 h-5 w-5" viewBox="0 0 20 20" fill="currentColor">
            <path
              fill-rule="evenodd"
              d="M5.23 7.21a.75.75 0 011.06.02L10 11.168l3.71-3.938a.75.75 0 111.08 1.04l-4.25 4.5a.75.75 0 01-1.08 0l-4.25-4.5a.75.75 0 01.02-1.06z"
              clip-rule="evenodd"
            />
          </svg>
          Cargar más historias
        </button>

        <div
          v-if="spinner"
          class="flex items-center rounded-full border border-primary-300 bg-primary-950 px-4 py-2 text-sm font-medium text-primary-100"
        >
          <svg
            class="w-5 h-5 mr-3 text-primary-200 animate-spin"
            viewBox="0 0 100 101"
            fill="none"
          >
            <circle
              cx="50"
              cy="50"
              r="45"
              stroke="currentColor"
              stroke-width="10"
              fill="transparent"
            />
          </svg>
          Cargando...
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped></style>
