<template>
    <div class = "loginHomePage">

        <div class = "topBarProstovoljci">
            <h1 class="headerHomeVol">Domaca stran</h1> 

            <div class="dropdown">
                <b-dropdown class=dropdownIcon text="Menu" size="lg" variant="info">
                    <b-dropdown-item href="/prostovoljciInbox">Nabiralnik</b-dropdown-item>
                    <b-dropdown-item href="/prostovoljciProfile">Profil</b-dropdown-item>
                    <b-dropdown-item href="/prostovoljciInfoZaDom">Aktivnosti</b-dropdown-item>
                    <b-dropdown-item href="/vstopnaStran">Odjava</b-dropdown-item>
                </b-dropdown>
            </div>
        </div>

        <div class = "underBarProstovoljci"> 

            
            <!--
            <form action="/prostovoljciInbox">
                <div class="form-group">
                <button class="btn btn-primary" :disabled="loading">
                    <span class="spinner-border spinner-border-sm" v-show="loading"></span>
                    <span>Nabiralnik</span>
                </button>
                </div>
            </form>

            <form action="/prostovoljciProfile">
                <div class="form-group">
                <button class="btn btn-primary" :disabled="loading">
                    <span class="spinner-border spinner-border-sm" v-show="loading"></span>
                    <span>Profil</span>
                </button>
                </div>
            </form>

            <form action="/prostovoljciInfoZaDom">
                <div class="form-group">
                <button class="btn btn-primary" :disabled="loading">
                    <span class="spinner-border spinner-border-sm" v-show="loading"></span>
                    <span>Aktivnosti</span>
                </button>
                </div>
            </form>

            <form action="/vstopnaStran">
                <div class="form-group">
                <button class="btn btn-primary" :disabled="loading">
                    <span class="spinner-border spinner-border-sm" v-show="loading"></span>
                    <span>Odjava</span>
                </button>
                </div>
            </form>-->
        
        </div> 
    </div>
</template>
