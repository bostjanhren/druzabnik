<template>
    <div class = "editProfile">

        <div class = "topBarProstovoljci">
            <h1 class="headerHomeVol">Moj Profil</h1>

            <div class="dropdown">
                <b-dropdown class=dropdownIcon text="Menu" size="lg" variant="info">
                    <b-dropdown-item href="/prostovoljciDoma" >Domovi</b-dropdown-item>
                    <!--<b-dropdown-item href="/prostovoljciInbox" >Sporočila</b-dropdown-item>-->
                    <b-dropdown-item href="/prostovoljciInbox">Sporočila</b-dropdown-item>
                    <b-dropdown-item href="/prostovoljciProfile">Profil</b-dropdown-item>
                    <!--<b-dropdown-item href="/prostovoljciInfoZaDom">Aktivnosti</b-dropdown-item>-->
                    <b-dropdown-item @click="odjavaClick">Odjava</b-dropdown-item>
                </b-dropdown>
            </div>
        </div>

        <div class = "underBarProstovoljciEditPage"> 
            <form>
                <div class="Slika">
                    <p>Prostor za dodajanje slike</p>
                    <button>Slika</button>
                </div>
            </form>

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
