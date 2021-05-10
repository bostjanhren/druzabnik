<template>
    <div class = "loginHomePage">

        <div class = "topBarProstovoljci">
            <h1 class="headerHomeVol">Domovi</h1> 

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
            <div v-for="blog in blogs" v-bind:key="blog" class="for-loop"> 
                <div>
                    <b-button class="homesBtn" v-b-toggle="'accordison-' + blog.homeName" variant="info">{{ blog.homeName }}</b-button>
                    <b-collapse :id="'accordison-' + blog.homeName" class="mt-2">
                        <b-card>
                            <p class="card-text">colapse content</p>
                        </b-card>
                    </b-collapse>
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

