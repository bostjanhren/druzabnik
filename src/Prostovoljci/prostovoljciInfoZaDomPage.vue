<template>
    <div>
        <h1>Informacije o domu</h1>

         <form action="/prostovoljciDoma">
            <div class="form-group">
            <button class="btn btn-primary" :disabled="loading">
                <span class="spinner-border spinner-border-sm" v-show="loading"></span>
                <span>Nazaj</span>
            </button>
            </div>
        </form>

        <form>
            <div class="form-group">
            <button class="btn btn-primary" :disabled="loading">
                <span class="spinner-border spinner-border-sm" v-show="loading"></span>
                <span>Podatke o domu in aktivnost</span>
            </button>
            </div>
        </form>

        <form action="/prostovoljciRegistracijaDom">
            <div class="form-group">
            <button class="btn btn-primary" :disabled="loading">
                <span class="spinner-border spinner-border-sm" v-show="loading"></span>
                <span>Rezerviraj</span>
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