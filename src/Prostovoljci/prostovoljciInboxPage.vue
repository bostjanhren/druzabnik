<template>
    <div class = "loginHomePage">

        <div class = "topBarProstovoljci">
            <h1 class="headerHomeVol">Sporočila</h1> 

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

        <div class = "underBarProstovoljci"> 
            <h2>Pogovori</h2>
            <div v-for="contact in contacts" v-bind:key="contact" class="for-loop-contacts"> 
                <div>
                    <b-button @click="contactClick(contact)" class="contactBtn" v-b-toggle="'gumbkontakt-' + contact.id">{{ contact.homeName }}</b-button>
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
             contacts:[]
        }),
        created(){
            var currentUser= JSON.parse(localStorage.getItem("currentUser"));
            console.log(this.currentUser);

            this.$http.get('https://druzabnikapi.herokuapp.com/messages').then(function(data){
                var messages = data.body;
                var currentid = currentUser.id;
                var newContacts = [];
                var newContactsDisp = [];
                //console.log(messages);
                messages.forEach(function(message) {
                    if(message.fromid == currentid){
                        
                        var novKontakt = message.toid;
                        if(!newContacts.includes(novKontakt)){
                            newContacts.push(novKontakt);
                        }
                    }
                })
                //id-ji kontaktov v newContacts
                //console.log(newContacts);
                this.$http.get('https://druzabnikapi.herokuapp.com/homes').then(function(data){
                    var homes = data.body;
                    homes.forEach(home=>{
                        if(newContacts.includes(home.id)){
                            newContactsDisp.push(home);
                        }
                    })
                })
                
                this.contacts = newContactsDisp;
                console.log(newContactsDisp);
            })
        },
        methods: {
            contactClick(contact){
                localStorage.removeItem('pickedHome');
                localStorage.setItem('pickedHome', JSON.stringify(contact));
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