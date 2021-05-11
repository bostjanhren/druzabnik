<template>
    <div class = "loginHomePage">

        <div class = "topBarProstovoljci">
            <h1 class="headerHomeVol">Sporočila</h1> 

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

        <div class = "underBarProstovoljci"> 
            <h2>Pogovori</h2>
            <div v-for="contact in contacts" v-bind:key="contact" class="for-loop-contacts"> 
                <div>
                    <b-button class="contactBtn" v-b-toggle="'gumbkontakt-' + contact.id">{{ contact.homeName }}</b-button>
                </div>
            </div>
        </div> 
    </div>
</template>

<script>
    import { handleResponse, requestOptions } from '../_helpers';
    export default {
        data: () => ({
             contacts:[]
        }),
        created(){
            this.$http.get('https://druzabnikapi.herokuapp.com/messages').then(function(data){
                var messages = data.body;
                var currentid = "609260f8d6b89a00157e97e3";
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
                console.log(newContactsDisp);
                this.contacts = newContactsDisp;

            })
        }
    }
</script>