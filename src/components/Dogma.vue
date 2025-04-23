<template>
  <section class="component p-10 mx-1 md:mx-10">
    <blockquote
      class="relative text-primary-900 text-center p-10 w-full m-1 text-3xl font-stretch-extra-expanded tracking-wide leading-10"
    >
      Renuncio al framework que no puedo pagar, al plugin de pago que nunca
      usaré, al CDN que carga en 3 segundos. Creo en la fuerza del localhost, en
      el poder del commit gratuito, y en la iluminación que solo da el bug que
      no se resuelve.
      <cite class="text-primary font-bold"> - Yampi</cite>
    </blockquote>
  </section>
</template>

<script setup></script>

<style scoped>
.component {
  font-family: "Helvetica Neue", "Helvetica", Helvetica, Arial, sans-serif;
}

blockquote {
  background: linear-gradient(to right, #7c6f64 6px, transparent 4px) 0 100%,
    linear-gradient(to left, #7c6f64 6px, transparent 4px) 100% 0,
    linear-gradient(to bottom, #7c6f64 6px, transparent 4px) 100% 0,
    linear-gradient(to top, #7c6f64 6px, transparent 4px) 0 100%;
  background-repeat: no-repeat;
  background-size: 20px 20px;
}

/* -- create the quotation marks -- */
blockquote:before,
blockquote:after {
  position: absolute;
  color: #7c6f64;
  font-size: 34px;
}
</style>
