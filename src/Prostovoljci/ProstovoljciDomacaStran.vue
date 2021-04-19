<template>
    <div>
        <h1>Prostovoljci Domaca stran</h1>
        <form action="/vpisProstovoljci">
            <div class="form-group">
            <button class="btn btn-primary" :disabled="loading">
                <span class="spinner-border spinner-border-sm" v-show="loading"></span>
                <span>Vpis</span>
            </button>
            </div>
        </form>
         <form action="/registracijaProstovoljci">
            <div class="form-group">
            <button class="btn btn-primary" :disabled="loading">
                <span class="spinner-border spinner-border-sm" v-show="loading"></span>
                <span>Registracija</span>
            </button>
            </div>
        </form>
    </div>
</template>
