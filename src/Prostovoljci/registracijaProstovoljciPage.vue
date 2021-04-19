<template>
  <div id="app">
    <h1>Registracija prostovoljca</h1>
    <form @submit.prevent="login">
      <div>
        <label for="username">uporabnisko ime</label>
        <input name="username" v-model="username" placeholder="username">
      </div>
      <div>
        <label for="password">geslo</label>
        <input name="password" v-model="password" placeholder="password" type="password">
      </div>
      <div>
        <label for="firstName">ime</label>
        <input name="firstName" v-model="firstName" placeholder="first name">
      </div>
      <div>
        <label for="lastName">priimek</label>
        <input name="lastName" v-model="lastName" placeholder="last name">
      </div>
<div>
        <label for="age">starost</label>
        <input name="age" v-model="age" placeholder="age" type="number">
      </div>
      <input type="submit" value="registracija">
    </form>
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