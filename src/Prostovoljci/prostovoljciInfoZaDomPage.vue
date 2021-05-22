<template>
    <div class = "loginHomePage">

        <div class = "topBarProstovoljci">
            <h1 class="headerHomeVol">O domu</h1> 

            <div class="dropdown">
                <b-dropdown class=dropdownIcon text="Menu" size="lg" variant="info">
                    <b-dropdown-item href="/prostovoljciDoma" >Domovi</b-dropdown-item>
                    <!--<b-dropdown-item href="/prostovoljciInbox" >Sporočila</b-dropdown-item>-->
                    <b-dropdown-item href="/prostovoljciInbox">Sporočila</b-dropdown-item>
                    <b-dropdown-item href="/prostovoljciProfile">Profil</b-dropdown-item>
                    <!--<b-dropdown-item href="/prostovoljciInfoZaDom">Aktivnosti</b-dropdown-item>-->
                    <b-dropdown-item @click="odjavaClick">Odjava</b-dropdown-item>
                </b-dropdown>
            </div>
        </div>

        <div class = "underBarIzbiraDoma">

                <div class= "HomeNameText">
                    <div class="homeIzbiraText">
                    <label>{{pickedHomename}}</label>
                    </div>
                    <div class="homeDescription">
                        <label >{{pickedHomeDescription}}</label>
                    </div>

                    <div class="btnODomu">

                        <!--
                        <form action="/">
                            <button class="btnHomeSelection">
                                Spoznaj Ekipo
                            </button>
                        </form>
                        -->
                            <form @submit.prevent="contactClick">
                                <button class="btnHomeSelection" >Pošlji sporočilo</button>
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
</template>

<script>
    import { router } from '@/_helpers';
    import { authenticationService } from '@/_services';

    export default {
        data: () => ({
             blogs:[],
             pickedHome,
             pickedHomename,
             pickedHomeDescription
        }),
        created(){
            this.$http.get('https://druzabnikapi.herokuapp.com/homes').then(function(data){
                this.blogs = data.body;
            })

            this.pickedHome= JSON.parse(localStorage.getItem("pickedHome"));
            this.pickedHomename = this.pickedHome.homeName;
            this.pickedHomeDescription = this.pickedHome.description;
            
        },
        methods: {
            contactClick(){
                console.log("click redirect")
                router.push('/prostovoljciMessage')
            },
            odjavaClick(){
                console.log("Odjava");
                authenticationService.logout();
                router.push("/vstopnaStran");
            }
        }
    }
</script>