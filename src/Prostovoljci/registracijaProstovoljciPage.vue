<template>
  <div class="registrationPageProstovoljci">
    <div class = "topbar"></div>
    <div class = "underbar">
      <label class = "registracijaProstovoljci1"> Registracija Prostovoljca </label>
      <form @submit.prevent="handleSubmit">
        <div class = "UporabniskoIme">
          <label class = "uporabniskoIme-text" for = "exampleUporabniskoIme"> Uporabnisko Ime </label>
          <input type = "uporabniskoIme" v-model="username" class = "form-control" id = "exampleUporabniskoIme1" aria-describedby="uporabniskoImeHelp" placeholder="Uporabnisko ime">
        </div>
        <div class = "Ime">
          <label class = "Ime-text" for = "exampleIme">  Ime </label>
          <input type = "Ime1" v-model="firstName" class = "form-control" id = "exampleIme1" aria-describedby="ImeHelp" placeholder="Ime">
        </div>
        <div class = "Priimek">
          <label class = "Priimek-text" for = "exampleIme">  Priimek </label>
          <input type = "Priimek1" v-model="lastName" class = "form-control" id = "examplePriimek1" aria-describedby="PriimekHelp" placeholder="Primek">
        </div>
        <div class="GesloProstovoljci">
          <label class= "GesloProstovoljci-text" for="exampleInputPassword1">Geslo</label>
          <input type="GesloProstovoljci1" v-model="password" class="form-control" id="exampleInputPassword1" placeholder="Geslo">
        </div>
        <button id="btnRegistracijaProstovoljci" type="submit">Registracija</button>
      </form>
      <br>
      <form action = "/">
        <button id="btnNazaj3" type="submit">Nazaj</button>
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
      password: "",
      firstName: "",
      lastName: ""
    };
  },
  methods: {
        handleSubmit () {
          var user = 
          {
              "username": this.username,
              "firstName": this.firstName,
              "lastName": this.lastName,
              "password": this.password
          }
          authenticationService.registerUser(user).then( data =>{
            console.log("done")
            authenticationService.login(this.username, this.password)
                .then(
                    user => router.push('/prostovoljciDoma'),
                    error => {
                      console.log("error")
                    }
                );
          });
        }
    }
};
</script>