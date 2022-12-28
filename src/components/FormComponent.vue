<template>
  <h3>{{ title }}</h3>
  <!-- Form -->
  <div class="form-group">
    <label for="name-field">Name <span class="required">(required)</span></label>
    <br />
    <input type="text" id="name-field" v-model="name" />
  </div>
  <div class="form-group">
    <label for="email-field">Email <span class="required">(required)</span></label>
    <br />
    <input type="text" id="email-field" v-model="email" />
  </div>
  <div class="form-group">
    <label for="message-field">Votre message :</label>
    <br />
    <textarea id="message-field" v-model="message"></textarea>
  </div>
  <button>Contact Us</button>
</template>

<style scoped>
.form-group {
  width: 100%;
  margin: 10px 0px;
}

.form-group input {
  width: 100%;
  padding: 10px;
  font-family: "PT Sans", -apple-system, BlinkMacSystemFont, "Segoe UI", "Roboto", "Oxygen", "Ubuntu", "Cantarell", "Fira Sans", "Droid Sans", "Helvetica Neue", sans-serif;
}

.form-group textarea {
  width: 100%;
  padding: 10px;
  min-height: 200px;
  font-family: "PT Sans", -apple-system, BlinkMacSystemFont, "Segoe UI", "Roboto", "Oxygen", "Ubuntu", "Cantarell", "Fira Sans", "Droid Sans", "Helvetica Neue", sans-serif;
}

.required {
  font-size: 17px;
  font-weight: 400;
  color: rgb(48, 48, 48);
  opacity: 0.45;
}

button {
  color: white;
  background-color: rgb(18, 121, 190);
  font-size: 20px;
  font-weight: 700;
  font-family: "PT Sans", -apple-system, BlinkMacSystemFont, "Segoe UI", "Roboto", "Oxygen", "Ubuntu", "Cantarell", "Fira Sans", "Droid Sans", "Helvetica Neue", sans-serif;
  border: none;
  border-radius: 5px;
  padding: 16px 24px;
  cursor: pointer;
}
</style>

<script lang="ts">
export default {
  props: ["title"],
  data() {
    return {
      name: null,
      email: null,
      message: "",
    };
  },
};
</script>
