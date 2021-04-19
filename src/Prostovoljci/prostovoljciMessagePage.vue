<template>
    <div>
        <h1>Rezerviraj</h1>

         <form action="/prostovoljciInbox">
            <div class="form-group">
            <button class="btn btn-primary" :disabled="loading">
                <span class="spinner-border spinner-border-sm" v-show="loading"></span>
                <span>Nazaj</span>
            </button>
            </div>
        </form>

        <form>
            <div class="form-group">
             <label for="Porocila">Porocilo</label>
             <input name="Porocila" v-model="firstName" placeholder="Porocila">
            </div>
        </form>

    </div>
</template>