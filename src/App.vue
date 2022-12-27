<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <header>
    <div class="wrapper">
      <h1>Rafinato Equine Dentistery</h1>
      <span id="subtitle">Linda Groot – Technicienne Dentaire Equin</span>
    </div>
  </header>

  <RouterView />

  <footer>
    <p>Rafinato Equine Dentistery</p>
  </footer>
</template>

<style scoped>

header{
  width: 100%;
  margin-top: 32px;
  margin-bottom: 32px;
}

.wrapper{
  width: 80%;
  margin: auto;
}

h1 {
  font-style: bold;
  margin-bottom: 0px;
}

#subtitle {
  margin-top: 0px;
  color: #757575;
  font-size: 0.75614rem;
  font-family: "PT Sans", -apple-system, BlinkMacSystemFont, "Segoe UI", "Roboto", "Oxygen", "Ubuntu", "Cantarell", "Fira Sans", "Droid Sans", "Helvetica Neue", sans-serif;
  font-weight: 400;
}

footer {
  display: flex;
  align-items: center;
  justify-content: center;
  font-weight: bold;
}
</style>
