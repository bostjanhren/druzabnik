<template>
    <div>
        <h1>Moje Sporocila</h1>

         <form action="/prostovoljciDoma">
            <div class="form-group">
            <button class="btn btn-primary" :disabled="loading">
                <span class="spinner-border spinner-border-sm" v-show="loading"></span>
                <span>Doma</span>
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

        <form action = "/prostovoljciMessage">
            <div class="form-group">
            <button class="btn btn-primary" :disabled="loading">
                <span class="spinner-border spinner-border-sm" v-show="loading"></span>
                <span>Sporocila</span>
            </button>
            </div>
        </form>

        <form action="/vstopnaStran">
            <div class="form-group">
            <button class="btn btn-primary" :disabled="loading">
                <span class="spinner-border spinner-border-sm" v-show="loading"></span>
                <span>Izpis</span>
            </button>
            </div>
        </form>

    </div>
</template>
