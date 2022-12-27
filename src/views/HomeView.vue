<script setup lang="ts">
  import FormComponentVue from '@/components/FormComponent.vue';
  import SliderComponentVue from '@/components/SliderComponent.vue';
</script>

<template>
  <main>
    <div class="row intro">
      <p>You are your own success.</p>
    </div>
    <div class="row">
      <div class="container">
        <h2>Faites controler les dents de vos chevaux!</h2>
        <p>Un mauvais entretien de la dentition de votre compagnon équin peut avoir des implications au niveau de son état de santé en général. Pour éviter des problèmes, un contrôle annuel est non seulement souhaitable mais fortement recommandé.
        </p>
        <p>Certains symptômes sont plus visibles que d’autres et il est même possible que votre cheval n’en montre aucun :
        </p>
        <ul>
          <li>Changement du comportement alimentaire, manque d’appétit</li>
          <li>Difficultés à la mastication et/ou difficultés à mâcher les aliments durs</li>
          <li>Foin et herbe mastiqués en petits rouleaux</li>
          <li>Salivation augmentée et/ou halitose</li>
          <li>Écoulement nasal, généralement unilatéral</li>
          <li>Bosses sur la tête et/ou sur les mâchoires</li>
          <li>Diarrhée, particules de fourrage non digérées dans les crottins, coliques</li>
          <li>Amaigrissement, pelage terne et mat</li>
          <li>Changement de comportement</li>
          <li>Secoue la tête, refus à être bridé</li>
          <li>Difficultés sous la selle</li>
          <li>Contractures, problèmes de dos, boiteries</li>
        </ul>
        <!-- Slider -->
        <SliderComponentVue />
        <img src="../assets/img/horse-jump.jpg" />
        <hr />
      </div>
    </div>
    <div class="row contact">
      <div class="container">
        <div class="col">
          <h3>Rafinato Equine Dentistery</h3>
          <p>40D Rue de Clairefontaine</p>
          <p>L-8460 Eischen</p>
          <p>Luxemburg</p>
          <p id="diploma">Linda Groot – Technicienne Dentaire Equin diplomée de l’Ecole Européenne de Dentisterie Equine.</p>
          <a href="tel:00352621966271">00352 621 966 271</a>
          <br />
          <a href="mailto:linda.groot@rafinato.lu">linda.groot@rafinato.lu</a>
        </div>
        <div class="col">
          <FormComponentVue title="Contact" />
        </div>
      </div>
      <div id="smile">
        <img src="../assets/img/horse-smile.jpg" />
      </div>
    </div>
  </main>
</template>

<style scoped>
.row {
  width: 100%;
  padding-top: 32px;
  padding-bottom: 32px;
}

.intro {
  display: flex;
  align-items: flex-end;
  justify-content: flex-end;
  height: 80vh;
  background-image: url("../assets/img/horse-in-box.jpg");
  background-size: cover;
  font-weight: 400;
  font-size: 26.45px;
  color: rgb(48, 48, 48);
  font-family: "PT Sans", -apple-system, BlinkMacSystemFont, "Segoe UI", "Roboto", "Oxygen", "Ubuntu", "Cantarell", "Fira Sans", "Droid Sans", "Helvetica Neue", sans-serif
}

.container {
  width: 60%;
  margin: auto;
}

.col {
  width: 50%;
  float: left;
}

img {
  width: 100%;
  background-size: cover;
}

.form-group {
  display: block;
}

.contact {
  background-color: rgb(248, 248, 248);
}

#smile {
  display: flex;
  width: 100%;
}

#smile img {
  margin: 32px auto;
  width: 40%;
}

#diploma {
  font-weight: 700;
}
</style>
