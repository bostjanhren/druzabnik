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
                        <label >{{ blog.description }}</label>
                    </div>

                    <div class="btnODomu">

                        <form action="/">
                            <button class="btnHomeSelection">
                                Spoznaj Ekipo
                            </button>
                        </form>
                        
                            <form action="/prostovoljciRegistracijaDom">
                                <button class="btnHomeSelection">Pošlji sporočilo</button>
                            </form>
                        
                        

                        <form action="/vstopnaStran">
                            <button class="btnHomeSelection">
                                Izberi termin
                            </button>
                        </form>
                    </div>

                </div>

                
        
            </div>

            

            

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