<template>
    <div class = "urejanjeTerminov">
        <div class = "topBarProstovoljci">
            <h1 class="headerHomeVol">Dodajanje novega termina</h1> 

            <div class="dropdown">
                <b-dropdown class=dropdownIcon text="Menu" size="lg" variant="info">
                    <b-dropdown-item href="/nabiralnikdom">Sporočila</b-dropdown-item>
                    <b-dropdown-item href="/profilnastrandom">Profil</b-dropdown-item>
                    <b-dropdown-item href="/domdolocitermin">Termini</b-dropdown-item>
                    <b-dropdown-item href="/vstopnaStran">Odjava</b-dropdown-item>
                </b-dropdown>
            </div>
        </div>
        <div class = "underBarProstovoljci">
            <div class="datePick">
                <input style="font-size: 2rem" type="date" v-model="date" id="date" placeholder=" 15:00">
                <div>
                    {{ date }}
                </div>
            </div> 

            <div class="timeInput">
                <input style="font-size: 2rem" type="time" v-model="time" id="time" placeholder=" 15:00">
                <div>
                    {{ time }}
                </div>
            </div>
            <div class="dodajTermin"><button @click="dodajTermin()">DodajTermin</button></div>
            
            
        </div>

    </div>
</template>

<script>
    export default {

        data: () => ({
            date: '',
            time: '',
            currentUser: ''

        }),
        created(){
            this.currentUser= JSON.parse(localStorage.getItem("currentUser"));
        },
        methods: {
            dodajTermin(){
                console.log(this.date, "is my date and", this.time, "is my time and my current user is", this.currentUser.id)
                this.$http.post('https://druzabnikapi.herokuapp.com/events',{
                    appointmentDateTime: this.date,
                    homeid: this.currentUser.id,
                    times: this.time
                })
            }
        }
    }
</script>
