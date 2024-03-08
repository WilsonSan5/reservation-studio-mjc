<script setup>
import CalendlyComponent from "./components/CalendlyComponent.vue";
import AccordeonMenuComponent from "./components/AccordeonMenuComponent.vue";
import FooterComponent from "./components/FooterComponent.vue";
import ScrollTopButton from "./components/ScrollTopButton.vue"
</script>

<template>
  <div class="container">
    <h1>Réserve ton&nbsp;créneaux&nbsp;!</h1>
    <h2>Studio de musique, MJC Boris Vian</h2>
  </div>
  <CalendlyComponent />
  <AccordeonMenuComponent />
  <FooterComponent />
  <ScrollTopButton />
</template>

<style scoped>
h1 {
  font-size: 3em;
}

h2 {
  font-size: 1.1em;
  margin-top: 10px;
  text-align: left;
  font-weight: 600;
}

.bottom {
  position: absolute;
  bottom: 0;
}

@media (min-width: 375px) {
  h1 {
    font-size: 3.5em;
  }

  h2 {
    font-size: 1.2em;
  }
}
</style>
