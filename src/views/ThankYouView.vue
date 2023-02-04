<template>
<<<<<<< HEAD
    <div class="container">
        <p>Merci, de nous avoir contacté nous traitons votre demande dans les plus brefs délais</p>
    </div>
    <div class="container">
        <p>Recapitulatif de votre demande de rendez vous:</p>
        <div class="col-6">
            <h2>Vos coordonnées:</h2>
            <p>Nom: {{ lastname }}</p>
            <p>Prénom: {{ firstname }}</p>
            <p>Tel: {{ phoneNumber }}</p>
            <p>Email: {{ emailAddress }}</p>
        </div>
        <div class="col-6">
            <h2>Le rendez vous:</h2>
            <p>Adresse: {{ address.street }}</p>
            <p>Code postale: {{ address.postcode }}</p>
            <p>Ville: {{ address.city }}</p>

            <p>Date: {{ date }}</p>
            <p>Time: {{ time }}</p>
        </div>
        <q-btn color="primary" label="Retour accueil" to="/"/>
    </div>
</template>

<script lang="ts">

export default {
    data: function () {
        return {
            lastname: "test",
            firstname: "test",
            phoneNumber: "0245857485",
            emailAddress: "test@test.com",
            address: {
                street: "test street",
                city: "test city",
                postcode: "52000"
            },
            date: "2023-01-14",
            time: "12:15"
        }
    }
}
</script>

<style lang="scss" scoped>
.container {
    width: 60%;
    margin: 15px auto ;
    background-color: lightgrey;
    padding: 20px;
    border-radius: 10px;
}

.col-6 {
    width: 50%;
    float: left;
}
</style>
=======
    <p>Hello</p>
</template>
>>>>>>> 06b896a36d794ee9181bdeda55cb59976a7ae732
