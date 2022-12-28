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
    <div class="container">
      <div class="row signature">
        <p>Rafinato Equine Dentistery</p>
      </div>
      <div class="row social">
        <p>Retrouvez nous sur:</p>
          <ul>
            <li v-for="link in socialLinks" v-bind:key="link.id">
              <a :href="link.link" :target="link.target" :alt="link.alt"><img :src="link.logo" /></a>
            </li>
          </ul>
      </div>
    </div>
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
  width: 100%;
}

.signature {
  padding: 15px;
  align-items: center;
  text-align: center;
  font-weight: bold;
}

.social p {
  font-size: 16px;
}

.social ul{
  display: flex;
  justify-items: center;
  align-items: center;
  justify-content: center;
}

.social ul li {
  display: inline;
  list-style: none;
  margin: 10px;
}

.social ul li img {
  width: 32px;
}


#fb-logo {
  width: 58px;
}

#fb-logo img{
  width: 32px;
}
</style>

<script lang="ts">
export default {
  data: () => {
    return {
      socialLinks: [
        {
          id: 1,
          link: "https://www.facebook.com/linda.groot.944",
          target: "_blank",
          logo: "./src/assets/img/f_logo_58.png",
          alt: "Logo facebook",
        },
      ],
    };
  },
}
</script>