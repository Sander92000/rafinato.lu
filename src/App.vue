<template>
  <q-layout view="lHh Lpr lFf">
    <q-header id="header">
        <q-toolbar-title>
          <h1>Rafinato Equine Dentistery <small>Linda Groot – Technicienne Dentaire Equin</small></h1>
        </q-toolbar-title>
    </q-header>

    <q-page-container>
      <router-view></router-view>
    </q-page-container>

    <footer>
      <p>Footer</p>
    </footer>

  </q-layout>
</template>

<style lang="scss">

#header {
  background: #fff;
  margin-top: 32px;
  margin-bottom: 32px;
}
small {

}
</style>