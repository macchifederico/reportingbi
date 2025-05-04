<!-- filepath: src/components/ContactSection.vue -->
<template>
    <section class="contact-section">
      <h2>Contáctanos</h2>
      <form id="contact-form" @submit.prevent="submitForm">
        <input type="text" v-model="name" placeholder="Tu nombre" required />
        <input type="email" v-model="email" placeholder="Tu correo electrónico" required />
        <textarea v-model="message" placeholder="Tu mensaje" required></textarea>
        <button type="submit" :disabled="isSending">
          {{ isSending ? 'Enviando...' : 'Enviar' }}
        </button>
      </form>
      <p v-if="successMessage" class="success-message">{{ successMessage }}</p>
      <p v-if="errorMessage" class="error-message">{{ errorMessage }}</p>
    </section>
  </template>
  
  <script lang="ts">
  import { defineComponent, ref } from 'vue';
  import emailjs from '@emailjs/browser';
  
  export default defineComponent({
    name: 'ContactSection',
    setup() {
      const name = ref('');
      const email = ref('');
      const message = ref('');
      const isSending = ref(false);
      const successMessage = ref('');
      const errorMessage = ref('');
  
      const submitForm = async () => {
      isSending.value = true;
      successMessage.value = '';
      errorMessage.value = '';

      try {
        const templateParams = {
          name: name.value,
          email: email.value,
          message: message.value,
        };

        // Reemplaza 'YOUR_SERVICE_ID', 'YOUR_TEMPLATE_ID' y 'YOUR_USER_ID' con tus valores de EmailJS
        await emailjs.send(
          'YOUR_SERVICE_ID',
          'YOUR_TEMPLATE_ID',
          templateParams,
          'YOUR_USER_ID'
        );

        successMessage.value = '¡Correo enviado con éxito! Pronto nos pondremos en contacto.';
        name.value = '';
        email.value = '';
        message.value = '';
      } catch (error) {
        console.error('Error al enviar el correo:', error);
        errorMessage.value = 'Hubo un error al enviar el correo. Por favor, inténtalo de nuevo.';
      } finally {
        isSending.value = false;
      }
    };
  
      return { name, email, message, isSending, successMessage, errorMessage, submitForm };
    },
  });
  </script>
