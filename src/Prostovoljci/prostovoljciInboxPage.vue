<template>
    <div>
        <h1>Moja Sporocila</h1>

         <form action="/prostovoljciDoma">
            <div class="form-group">
            <button class="btn btn-primary" :disabled="loading">
                <span class="spinner-border spinner-border-sm" v-show="loading"></span>
                <span>Domov</span>
            </button>
            </div>
        </form>

        <br>

        <p>
            Prostor kjer nam bo pokazalo tekoče pogovore / vse prej ustvarjene pogovore z vsako osebo posebej.
        </p>

        <form action = "/instancaSporocilaProstovoljec">
            <button type="submit" class="btn btn-secondary">Chat z osebo xxxxx</button>
        </form>

    </div>
</template>
