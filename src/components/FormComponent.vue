<template>
  <h3>{{ title }}</h3>
  <form ref="form">
    <q-input outlined v-model="name" label="Votre nom" name="user_name" />
    <q-input outlined v-model="email" label="Votre adresse email" name="user_email"/>
    <label>Votre message:</label>
    <textarea name="message" v-model="message"></textarea>
    <q-btn :loading="loading" color="primary" @click="sendEmail">
      Envoyer
      <template v-slot:loading>
        <q-spinner-hourglass class="on-left" />
        Envoi...
      </template>
    </q-btn>
  
  </form>
</template>

<style lang="scss" scoped>
input {
  width: 100%;
}

textarea {
  width: 100%;
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
      loading: false,
    };
  },
  methods: {
    sendEmail() {
      console.log('click');
      this.loading = true;
      /*
      emailjs.sendForm(this.emailJS.serviceId, 
                       this.emailJS.templateId, 
                       this.$refs.form, 
                       this.emailJS.publicKey)
      .then((result) => {
        console.log('success');
      }).catch( (error) => {
        console.log(error);
      }); */
    },
  },
};
</script>
