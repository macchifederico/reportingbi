<!-- filepath: src/components/HeroSection.vue -->
<template>
  <section class="hero-section">
    <div class="hero-content">
      <h1>Servicios de Reportes y Dashboards</h1>
      <p>Transforma tus datos en decisiones con Power BI.</p>
      <button @click="contactUs">Contáctanos</button>
    </div>
    <!-- <img src="@/assets/images/hero-section.jpg" alt="Hero Image" /> -->
  </section>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'HeroSection',
  methods: {
    contactUs() {
      const contactForm = document.getElementById('contact-form');
      if (contactForm) {
        contactForm.scrollIntoView({ behavior: 'smooth' });
      }
    },
  },
});
</script>

