<template>
    <div>
        <h1>Moj Profil</h1>

         <form>
            <div class="form-group">
            <button class="btn btn-primary" :disabled="loading">
                <span class="spinner-border spinner-border-sm" v-show="loading"></span>
                <span>Uredi</span>
            </button>
            </div>
        </form>

         <form>
            <div class="form-group">
            <label for="Slika">Slika</label>
            <input name="Slika" v-model="firstName" placeholder="Slika">
            </div>
        </form>

         <form>
            <div class="form-group">
             <label for="Ime, Priimek, Starost">Ime, Priimek, Starost</label>
             <input name="Ime, Priimek, Starost" v-model="firstName" placeholder="Ime, Priimek, Starost">
            </div>
        </form>

         <form>
            <div class="form-group">
            <label for="O meni">O meni</label>
             <input name="O meni" v-model="firstName" placeholder="O meni">
            </div>
        </form>

        <form action="/prostovoljciDoma">
            <div class="form-group">
            <button class="btn btn-primary" :disabled="loading">
                <span class="spinner-border spinner-border-sm" v-show="loading"></span>
                <span>Doma</span>
            </button>
            </div>
        </form>

    </div>
</template>
