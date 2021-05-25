<template>
    <div class = "loginHomePage">

        <div class = "topBarDomovi">
            <h1 class="headerHome">Domovi</h1> 

            <div class="dropdownDom">
                <input id="dropcheck" class="dropcheck" type="checkbox">
                <label for="dropcheck" class="dropbtn"></label>
                <div class="dropdown-content">
                    <a href="/nabiralnikdom">Sporočila</a>
                    <a href="/profilnastrandom">Profil</a>
                    <a href="/domdolocitermin">Termini</a>
                    <a @click="odjavaClick">Odjava</a>
                </div>
            </div>
        </div>


            <div class="dropdown">
                <b-dropdown class=dropdownIcon text="Menu" size="lg" variant="info">
                    <b-dropdown-item href="/nabiralnikdom">Sporočila</b-dropdown-item>
                    <b-dropdown-item href="/profilnastrandom">Profil</b-dropdown-item>
                    <b-dropdown-item href="/domdolocitermin">Termini</b-dropdown-item>
                    <b-dropdown-item href="/vstopnaStran">Odjava</b-dropdown-item>
                </b-dropdown>
            </div>



        <div class = "underbar"> 


            <p>
                Dummy text
            </p>

        </div>
    </div>
</template>