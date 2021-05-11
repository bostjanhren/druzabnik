<template>
  <div class="registrationPageProstovoljci">
    <div class = "topbar"></div>
    <div class = "underbar">
      <label class = "registracijaProstovoljci1"> Registracija Prostovoljca </label>
      <form>
        <div class = "UporabniskoIme">
          <label class = "uporabniskoIme-text" for = "exampleUporabniskoIme"> Uporabnisko Ime </label>
          <input type = "uporabniskoIme" class = "form-control" id = "exampleUporabniskoIme1" aria-describedby="uporabniskoImeHelp" placeholder="Uporabnisko ime">
        </div>
        <div class = "Ime">
          <label class = "Ime-text" for = "exampleIme">  Ime </label>
          <input type = "Ime1" class = "form-control" id = "exampleIme1" aria-describedby="ImeHelp" placeholder="Ime">
        </div>
        <div class = "Priimek">
          <label class = "Priimek-text" for = "exampleIme">  Priimek </label>
          <input type = "Priimek1" class = "form-control" id = "examplePriimek1" aria-describedby="PriimekHelp" placeholder="Primek">
        </div>
        <div class="GesloProstovoljci">
          <label class= "GesloProstovoljci-text" for="exampleInputPassword1">Geslo</label>
          <input type="GesloProstovoljci1" class="form-control" id="exampleInputPassword1" placeholder="Geslo">
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
export default {
  name: "App",
  data() {
    return {
      username: "",
      password: "",
      firstName: "",
      lastName: "",
      age: "",
    };
  },
  methods: {
    async login() {
      const { username, password, firstName, lastName, age } = this;
      const res = await fetch(
        "https://SomberHandsomePhysics--five-nine.repl.co/register",
        {
          method: "POST",
          headers: {
            "Content-Type": "application/json"
          },
          body: JSON.stringify({
            username,
            password,
            firstName,
            lastName,
            age
          })
        }
      );
      const data = await res.json();
      console.log(data);
    }
  }
};
</script>