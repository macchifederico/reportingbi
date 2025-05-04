<!-- filepath: src/components/LandingPage.vue -->
<template>
  <div class="landing-page">
    <HeroSection />
    <FeaturesSection />
    <ContactSection />
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import HeroSection from '../components/HeroSection.vue';
import FeaturesSection from '../components/FeaturesSection.vue';
import ContactSection from '../components/ContactSection.vue';

export default defineComponent({
  name: 'LandingPage',
  components: {
    HeroSection,
    FeaturesSection,
    ContactSection,
  },
});
</script>

<style scoped>
/* Puedes agregar estilos específicos aquí si es necesario */
</style>