<template>
  <q-layout view="lHh Lpr lFf">
    <q-header id="page-header" elevated class="glossy">
      <h1>Rafinato Equine Dentistery</h1>
      <p>Linda Groot – Technicienne Dentaire Equin</p>
      <q-btn color="primary" label="Demande rendez-vous" />
    </q-header>

    <q-page-container id="page-container">
      <router-view></router-view>
    </q-page-container>

    <q-footer id="page-footer">
      <p>Sander</p>
    </q-footer>
  </q-layout>
</template>

<script>
import { ref } from 'vue'

export default {
  name: 'LayoutDefault',

  components: {
  },

  setup () {
    return {
    }
  }
}
</script>

<style lang="scss" scoped>
#page-header{
  padding: 15px;
  background-color: #fff;
}

#page-container {
  padding-top: 0px !important;
  padding-bottom: 0px !important;
}

#page-footer {
  padding: 15px;
  background-color: #fff;
}
</style>
