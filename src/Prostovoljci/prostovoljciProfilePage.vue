<template>
    <div class = "editProfile">

        <div class = "topBarProstovoljci">
            <h1 class="headerHomeVol">PROFIL</h1>

            <div class="dropdown">
                <input id="dropcheck" class="dropcheck" type="checkbox">
                <label for="dropcheck" class="dropbtn"></label>
                <div class="dropdown-content">
                    <a href="/prostovoljciDoma">Domovi</a>
                    <a href="/prostovoljciInbox">Sporočila</a>
                    <a href="/prostovoljciProfile">Profil</a>
                    <a @click="odjavaClick">Odjava</a>
                </div>
            </div>
            
        </div>

        <div class = "underBarProstovoljciEditPage"> 


            <div class="ImeEdit">
                <label class= "email-text" for="exampleInputEmail1"> Ime </label>
                <input type="uporabniskoIme" v-model="username" class="form-control" id="exampleInputEmail1" aria-describedby="emailHelp" placeholder="Ime">
            </div>
            <div class="PriimekEdit">
                <label class= "geslo-text" for="exampleInputPassword1">Priimek</label>
                <input type="password" v-model="password" class="form-control" id="exampleInputPassword1" placeholder="Priimek">
            </div>
            <div class="Starost">
                <label class= "email-text" for="exampleInputEmail1"> Starost </label>
                <input type="uporabniskoIme" v-model="username" class="form-control" id="exampleInputEmail1" aria-describedby="emailHelp" placeholder="Vnesi email">
            </div>
            <div class="Opis">
                <label class= "geslo-text" for="exampleInputPassword1">Opis</label>
                <input type="password" v-model="password" class="form-control" id="exampleInputPassword1" placeholder="Geslo">
            </div>

            <!--- TODO: urediti fielde in pullat info od current logged in userja in slika-->

            <br>
            <br>
            <br>
            <br>

            <form>
                <div class="form-group">
                <button class="btn btn-primary" :disabled="loading">
                    <span class="spinner-border spinner-border-sm" v-show="loading"></span>
                    <span>Shrani</span>
                </button>
                </div>
            </form>

            <br>

            <form action="/prostovoljciDoma">
                <div class="form-group">
                <button class="btn btn-primary" :disabled="loading">
                    <span class="spinner-border spinner-border-sm" v-show="loading"></span>
                    <span>Domov</span>
                </button>
                </div>
            </form>

        </div>

    </div>
</template>

<script>
    import config from 'config';
    import { requestOptions, handleResponse } from '@/_helpers';
    import { router } from '@/_helpers';
    import { authenticationService } from '@/_services';
    export default {
        data(){
            return{
             
            }
        },
        created(){
            
        },
        methods: {
            odjavaClick(){
                console.log("Odjava");
                authenticationService.logout();
                router.push("/vstopnaStran");
            },
        }
    }
</script>