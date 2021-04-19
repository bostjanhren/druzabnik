<template>
    <div>
        <h1>DOMA</h1> 

        <form action="/prostovoljciInbox">
            <div class="form-group">
            <button class="btn btn-primary" :disabled="loading">
                <span class="spinner-border spinner-border-sm" v-show="loading"></span>
                <span>Sporocila</span>
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
                <span>Izpis</span>
            </button>
            </div>
        </form>

        <div>
           Trenuten uporabnik:
            <ul v-if="userFromApi">
                <li>{{userFromApi.firstName}} {{userFromApi.lastName}}</li>
            </ul>
        </div>
    </div>
</template>

<script>
import { userService, authenticationService } from '@/_services';

export default {
    data () {
        return {
            currentUser: authenticationService.currentUserValue,
            userFromApi: null
        };
    },
    created () {
        userService.getById(this.currentUser.id).then(user => this.userFromApi = user);
    }
};
</script>