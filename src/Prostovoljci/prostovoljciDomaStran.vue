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
            <span class="text">V-FOR...isce po dodanih lokacijah</span>
        
        </div> 
    </div>
</template>

