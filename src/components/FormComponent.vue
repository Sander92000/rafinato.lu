<template>
  <h3>{{ title }}</h3>
  <form ref="form" @submit.prevent="sendEmail">
    <p v-if="emailSuccess" class="alert alert-success">Merci pour votre message. Nous vous répondons dans les plus brefs délais.</p>
    <p v-if="emailError" class="alert alert-danger">Une erreur s'est produite. Veuillez essayer plus tard.</p>
    <input type="hidden" name="from_name" value="Rafinato - website"/>
    <div class="form-group">
      <label for="user-name">Votre nom : *</label>
      <input type="text" id="user-name" class="form-control" name="user_name" v-model="name" />
      <p v-if="nameFieldError" class="error-msg">Veillez renseigner votre nom.</p>
    </div>
    <div class="form-group">
      <label for="user-email">Votre adresse email : *</label>
      <input type="email" id="user-email" class="form-control" name="user_email" v-model="email" />
      <p v-if="emailFieldError" class="error-msg">Veillez renseigner votre adresse email.</p>
    </div>
    <label for="user-msg">Votre message:</label>
    <textarea class="form-control" id="user-msg" name="message" v-model="message"></textarea>
    <p id="mandatory">(*) champs obligatoires</p>
    <button type="submit">Envoyer</button>
  </form>
</template>

<style scoped>
input {
  width: 100%;
}

.input-error {
  border: 1px solid red;
}

.error-msg {
  font-size: 12px;
  color: red;
}

textarea {
  width: 100%;
  min-height: 200px;
}

#mandatory {
  font-size: 12px;
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
import { ref } from 'vue'
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
      nameFieldError: false,
      emailFieldError: false,
    };
  },
  methods: {
    sendEmail() {

      const nameInput = document.getElementById('user-name');
      const emailInput = document.getElementById('user-email');

      if(this.name == "") {
        nameInput.classList.add('input-error');
        this.nameFieldError = true;
        return true;
      } else {
        nameInput.classList.remove('input-error');
        this.nameFieldError = false;
      }

      if(this.email == ""){
        emailInput.classList.add('input-error');
        this.emailFieldError = true;
        return true;
      } else {
        this.emailFieldError = false;
        emailInput.classList.remove('input-error');
      }

      emailjs
        .sendForm(
          this.emailJS.serviceId,
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
