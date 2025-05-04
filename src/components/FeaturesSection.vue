<!-- filepath: src/components/FeaturesSection.vue -->
<template>
  <section class="features-section">
    <h2>Nuestros Servicios</h2>
    <div class="features">
      <div class="feature" v-for="feature in features" :key="feature.title">
        <h3>{{ feature.title }}</h3>
        <p>{{ feature.description }}</p>
      </div>
    </div>
  </section>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'FeaturesSection',
  data() {
    return {
      features: [
        { title: 'Reportes Personalizados', description: 'Diseñamos reportes a medida para tus necesidades.' },
        { title: 'Dashboards Interactivos', description: 'Visualiza tus datos de forma clara y dinámica.' },
        { title: 'Consultoría en Power BI', description: 'Te ayudamos a implementar soluciones efectivas.' },
      ],
    };
  },
});
</script>
