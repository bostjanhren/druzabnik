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
            <form class = "form-inline" id = "newMessage" action="placeholder">
                <input type="text" id="tekst" name="fname" value=""><br>
                <input type="submit" id = "tekstPoslji" value="Pošlji">
            </form> 
        </div> 
    </div>
</template>

<script>
    
    export default {
        data: () => ({
             messagesDisp:[]
        }),
        created(){
            var meId = "609260f8d6b89a00157e97e3";
            var toId = "60994558ad59e600150cfa07";
            var messagesSelected = [];
            this.$http.get('https://druzabnikapi.herokuapp.com/messages').then(function(data){
                var messages = data.body;
               
                messages.forEach(message => {
                    if(message.fromid == meId || message.fromid == toId || message.toid == meId || message.toid == toId){
                        messagesSelected.push(message);
                    }
                });
            })
            this.messagesDisp = messagesSelected;
        }
    }
</script>