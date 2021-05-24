<template>
    <div class = "urejanjeTerminov">
        <div class = "topBarProstovoljci">
            <h1 class="headerHomeVol">Urejanje terminov za obsike</h1> 

            <div class="dropdown">
                <input id="dropcheck" class="dropcheck" type="checkbox">
                <label for="dropcheck" class="dropbtn"></label>
                <div class="dropdown-content">
                    <a href="/prostovoljciDoma">Domovi</a>
                    <a href="/prostovoljciInbox">Sporočila</a>
                    <a href="/prostovoljciProfile">Profil</a>
                    <a @click="odjavaClick">Odjava</a>
                </div>
            </div>

        </div>

        <div class = "underBarProstovoljci"> 

            {{ create2DList(blogs, pickedHome.id) }}

            <div v-for="(date, index) in listDates" v-bind:key="date" class="for-loop"> 
                
                <div>
                    <b-button class="homesBtn" v-b-toggle="'accordison-' + date">{{ dateSplit(date) }}</b-button>
                    <b-collapse :id="'accordison-' + date" :class="'accordison-' + date">
                        <div v-for="time in listTimes[index]" v-bind:key="time">
                            <label  class= "HomeNameText">{{ time }}</label>
                            <button>izberi ta termin</button>
                        </div>
                        
                        <div>
                            <!--<p @click="onHomeClick(blog.homeName)" tag="button" class = "btnHomeSelect">Izberi</p>-->
                        </div>    
                    </b-collapse>
                </div>
            </div>
        </div>

    </div>
</template>

<script>
    export default {
        data: () => ({
             pickedHome: "",
             blogs:[],
             listDates:[],
             listTimes: []
        }),
        created(){
            this.$http.get('https://druzabnikapi.herokuapp.com/events').then(function(data){
                this.blogs = data.body;
            })
            this.pickedHome= JSON.parse(localStorage.getItem("pickedHome"));
        },
        methods: {
            odjavaClick(){
                console.log("Odjava");
                authenticationService.logout();
                router.push("/vstopnaStran");
            },
            dateSplit(date){
                var res = date.split("T");
                var res2 = res[0].split("-");
                var res3 = res2[2] + "." + res2[1] + "." + res2[0];
                return res3
            },
            create2DList(data, homeID){
                var listOfDates = []
                var i;
                for(i = 0; i < data.length; i++){
                    if(data[i].homeid == homeID){
                        if(!listOfDates.includes(data[i].appointmentDateTime)){
                            listOfDates.push(data[i].appointmentDateTime)
                        }
                    }   
                }
                var arrayWithTimes = []
                var times = []
                var j;
                for(j = 0; j < listOfDates.length; j++){
                    for(i = 0; i < data.length; i++){
                        if(data[i].homeid == homeID){
                            if (data[i].appointmentDateTime == listOfDates[j]){
                                if(!times.includes(data[i].times)){
                                    times.push(data[i].times)
                                }
                            } 
                        }
                    }
                    arrayWithTimes.push(times)
                    times = []
                }
                this.listTimes = arrayWithTimes
                this.listDates = listOfDates
                
            }
        }
    }
</script>
