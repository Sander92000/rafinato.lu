<template>
  <h3>{{ title }}</h3>
  <form ref="form" @submit.prevent="sendEmail">
    <p v-if="emailSuccess" class="alert alert-success">Merci pour votre message. Nous vous répondons dans les plus brefs délais.</p>
    <p v-if="emailError" class="alert alert-danger">Une erreur s'est produite. Veuillez essayer plus tard.</p>
    <input type="hidden" name="from_name" value="Rafinato - website"/>
    <label>Votre nom: *</label>
    <input type="text" id="user-name" name="user_name" v-model="name" />
    <label>Votre adresse email: *</label>
    <input type="email" id="user-email" name="user_email" v-model="email" />
    <label>Votre message:</label>
    <textarea name="message" v-model="message"></textarea>
    <button type="submit">Envoyer</button>
  </form>
</template>

<style scoped>
input {
  width: 100%;
}

textarea {
  width: 100%;
  min-height: 200px;
}

button {
  width: 100%;
  color: #fff;
  border: none;
  border-radius: 5px;
  background-color: #1279be;
  font-size: 20px;
  font-family: "PT Sans", -apple-system, BlinkMacSystemFont, "Segoe UI", "Roboto", "Oxygen", "Ubuntu", "Cantarell", "Fira Sans", "Droid Sans", "Helvetica Neue", sans-serif;
  padding: 16px 24px;
}

.alert{
  font-size: 12px;
}
</style>

<script lang="ts">
import emailjs from '@emailjs/browser';

export default {
  props: ["title"],
  data: function() {
    return {
      name: "",
      email: "",
      message: "",
      emailJS: {
        serviceId: import.meta.env.VITE_EMAIL_JS_SERVICE_ID,
        templateId: import.meta.env.VITE_EMAIL_JS_TEMPLATE_ID,
        publicKey: import.meta.env.VITE_EMAIL_JS_PUBLIC_KEY,
      },
      emailSuccess: false,
      emailError: false,
    };
  },
  methods: {
    sendEmail() {
      emailjs.sendForm(this.emailJS.serviceId, 
                       this.emailJS.templateId, 
                       this.$refs.form, 
                       this.emailJS.publicKey)
      .then((result) => {
        console.log('SUCCESS!', result.text);
        this.name = "";
        this.email = "";
        this.message = "";
        this.showEmailSuccess();
      }).catch( (error) => {
        console.log('FAILED...', error.text);
        this.showEmailError();
      });
    },
    showEmailSuccess() {
      this.emailSuccess = true;
      setTimeout(this.hideEmailSuccess, 10000);
    },
    hideEmailSuccess() {
      this.emailSuccess = false;
    },
    showEmailError() {
      this.emailError = true;
      setTimeout(this.hideEmailError, 10000);
    },
    hideEmailError() {
      this.emailError = false;
    },
  },
};
</script>
