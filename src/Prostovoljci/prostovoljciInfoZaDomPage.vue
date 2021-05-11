<template>
    <div class = "loginHomePage">

        <div class = "topBarProstovoljci">
            <h1 class="headerHomeVol">O domu</h1> 

            <div class="dropdown">
                <b-dropdown class=dropdownIcon text="Menu" size="lg" variant="info">
                    <b-dropdown-item href="/prostovoljciDoma" >Domovi</b-dropdown-item>
                    <b-dropdown-item href="/prostovoljciInbox" >Sporočila</b-dropdown-item>
                    <b-dropdown-item href="/prostovoljciProfile">Profil</b-dropdown-item>
                    <b-dropdown-item href="/prostovoljciInfoZaDom">Aktivnosti</b-dropdown-item>
                    <b-dropdown-item href="/vstopnaStran">Odjava</b-dropdown-item>
                </b-dropdown>
            </div>
        </div>

        <div class = "underBarIzbiraDoma">

            <div v-for="blog in blogs" v-bind:key="blog" class="for-loop"> 
                <div v-if="blog.homeName == $route.params.id" class= "HomeNameText">
                    <div class="homeIzbiraText">
                    <label >{{ $route.params.id }}</label>
                    </div>
                    <div class="homeDescription">
                        <label >{{ blog.desciption }}</label>
                    </div>


                </div>

                
            </div>

            
            

            <form>
                <div class="form-group">
                <button class="btn btn-primary" :disabled="loading">
                    <span class="spinner-border spinner-border-sm" v-show="loading"></span>
                    <span>Spoznaj Ekipo</span>
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
                    <span>Izberi termin</span>
                </button>
                </div>
            </form>

            

        </div>

        

    </div>
</template>

<script>
    export default {
        data: () => ({
             blogs:[]
        }),
        created(){
            this.$http.get('https://druzabnikapi.herokuapp.com/homes').then(function(data){
                this.blogs = data.body;
            })
        }
    }
</script>