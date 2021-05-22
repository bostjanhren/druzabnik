<template>
<div class = "loginProstovoljci">

    <div class = "topbar"></div>

    <div class = "underbar"> 

        <label class= "prijavaProstovoljci">Prijava Prostovoljci</label>
            
        <form @submit.prevent="handleSubmit">
            <div class="E-mail">
                <label class= "email-text" for="exampleInputEmail1"> Uporabnisko Ime </label>
                <input type="uporabniskoIme" v-model="username" class="form-control" id="exampleInputEmail1" aria-describedby="emailHelp" placeholder="Vnesi email">
            </div>
            <div class="Geslo">
                <label class= "geslo-text" for="exampleInputPassword1">Geslo</label>
                <input type="password" v-model="password" class="form-control" id="exampleInputPassword1" placeholder="Geslo">
            </div>
            <button id ="btnPrijava" type="submit">Prijava</button>
        </form>
        <br>
        <form action = "registracijaProstovoljci">
            <label class= "registracija-text">Ali še niste uporabnik?</label>
            <button id = "btnRegistracija" type="submit">Registracija</button>
        </form>

        <form action = "/">
                <button id="btnNazaj2" type="submit">Nazaj</button>
        </form>
    </div>
</div>
</template>

<script>
import { router } from '@/_helpers';
import { authenticationService } from '@/_services';

export default {
  name: "App",
  data() {
    return {
      username: "",
      password: ""
    };
  },
  methods: {
        handleSubmit () {
            console.log("Logging in " + this.username + " " + this.password)
        authenticationService.login(this.username, this.password)
            .then(
            user => router.push('/prostovoljciDoma'),
            error => {
            console.log("error")
            }
            );
          
        }
    }
};
</script>
