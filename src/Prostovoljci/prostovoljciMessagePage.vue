<template>
    <div id = "prostovoljciMessageStil">

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

        <div class = "underBarProstovoljciChat"> 
            <h2 id="chatTitle">Pogovor: Kranj</h2>

            <div id = "conversation">
                <div v-for="message in messagesDisp" v-bind:key="message" class="for-loop-messages"> 
                    <div v-if="message.fromid == '609260f8d6b89a00157e97e3'" class="messageRight">
                        
                            {{message.text}}
                        
                    </div>
                    <div v-else class="messageLeft">
                        
                            {{message.text}}
                        
                    </div>
                </div>
            </div>
            <div id = "bottomDiv">
            <form class = "form-inline" @submit.prevent="newMessageSubmit" id = "newMessage" action="placeholder">
                <input type="text" v-model="tekst" id="tekst" name="fname" value=""><br>
                <input type="submit" id = "tekstPoslji" value="Pošlji">
            </form>
            </div> 
        </div> 
    </div>
</template>

<script>
    import config from 'config';
    import { requestOptions, handleResponse } from '@/_helpers';
    import { router } from '@/_helpers';
    import { authenticationService } from '@/_services';
    export default {
        data(){
            return{
             messagesDisp:[],
             tekst:""
            }
        },
        created(){
            var meId = JSON.parse(localStorage.getItem("currentUser")).id;

            var toId = JSON.parse(localStorage.getItem("pickedHome")).id;
            var messagesSelected = [];
            this.$http.get('https://druzabnikapi.herokuapp.com/messages').then(function(data){
                var messages = data.body;
               
                messages.forEach(message => {
                    if(message.fromid == meId || message.fromid == toId || message.toid == meId || message.toid == toId){
                        messagesSelected.push(message);
                    }
                });
            })
            console.log(messagesSelected);
            this.messagesDisp = messagesSelected;
        },
        methods: {
            odjavaClick(){
                console.log("Odjava");
                authenticationService.logout();
                router.push("/vstopnaStran");
            },
            newMessageSubmit(){
                var message = {
                    "text": this.tekst,
                    "fromid": JSON.parse(localStorage.getItem("currentUser")).id,
                    "toid": JSON.parse(localStorage.getItem("pickedHome")).id
                }
                fetch(`${config.apiUrl}/messages`,requestOptions.post(message))
                    .then(handleResponse)
                    .then( data =>{
                        console.log("Sent: " + data)
                        this.tekst = "";
                        location.reload();
                    });
                
            }
        }
    }
</script>