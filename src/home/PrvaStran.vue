<template>
    <div>
        <h1>Druzabnik</h1>
        <form action="/prostovoljec">
            <div class="form-group">
            <button class="btn btn-primary" :disabled="loading">
                <span class="spinner-border spinner-border-sm" v-show="loading"></span>
                <span>Prostovoljci</span>
            </button>
            </div>
        </form>
        <form action="/prijavadom">
            <div class="form-group">
            <button class="btn btn-primary" :disabled="loading">
                <span class="spinner-border spinner-border-sm" v-show="loading"></span>
                <span>Domovi</span>
            </button>
            </div>
        </form>
    </div>
</template>