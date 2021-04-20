<template>
    <div>
        <h1>Moj Profil</h1>


         <form>
            <div class="form-group">
            <p>Prostor za dodajanje slike</p>
            <button>Slika</button>
            </div>
        </form>

         <form>
            <div class="form-group">
             <label for="Ime, Priimek, Starost">Ime</label>
             <input name="Ime, Priimek, Starost" v-model="firstName" placeholder="Ime">
            </div>
        </form>

        <form>
            <div class="form-group">
             <label for="Ime, Priimek, Starost">Priimek</label>
             <input name="Ime, Priimek, Starost" v-model="firstName" placeholder="Priimek">
            </div>
        </form>

        <form>
            <div class="form-group">
             <label for="Ime, Priimek, Starost">Starost</label>
             <input name="Ime, Priimek, Starost" v-model="firstName" placeholder="Starost">
            </div>
        </form>

         <form>
            <div class="form-group">
            <label for="O meni">O meni</label>
             <input name="O meni" v-model="firstName" placeholder="O meni">
            </div>
        </form>

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
</template>
