<template>
    <div>
        <h1>Sporocilo</h1>

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
             <label for="Sporocilo">Sporocilo</label>
             <input name="Sporocilo" v-model="firstName" placeholder="Sporocilo">
            </div>
        </form>

    </div>
</template>