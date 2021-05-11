<template>
  <div class = "registrationPageDomove">
    <div class = "topbar"></div>
    <div class = "underbar">
        <label class = "registracijaDom"> Registracija Doma </label>
        <label class = "registracijaDom-tekst"> Prosim vnesite podatke vaše ustanove </label>
        <form>
            <!-- ime doma upokojencev -->
            <div class = "registacijaImeDom">
                 <label class = "registracijaImeDom1-text" for = "exampleRegistracijaImeDom"> Ime dom </label>
                 <input type = "registracijaImeDom1" class = "form-control" id = "exampleRegistracijaImeDom1" aria-describedby="registracijaImeDomHelp" placeholder="Ime Dom">
            </div>

            <!--naslov doma upokojencev -->
            <div class = "registracijaNaslovDom">
                 <label class = "registracijaNaslovDom1-text" for = "exampleRegistracijaNaslovDom"> Naslov dom </label>
                 <input type = "registracijaNaslovDom1" class = "form-control" id = "exampleRegistracijaNaslovDom1" aria-describedby="registracijaNaslovDomHelp" placeholder="Naslov">
            </div>

           <!--E-postni naslov doma upokojencev -->
            <div class = "registracijaPostniNaslovDom">
                 <label class = "registracijaPostniNaslovDom1-text" for = "exampleRegistracijaPostniNaslovDom"> E-poštni naslov dom </label>
                 <input type = "registracijaPostniNaslovDom1" class = "form-control" id = "exampleRegistracijaPostniNaslovDom1" aria-describedby="registracijaPostniNaslovDomHelp" placeholder="E-poštni naslov">
            </div>

            <!--geslo doma upokojencev -->
            <div class = "registracijaGesloDom">
                 <label class = "registracijaGesloDom1-text" for = "exampleRegistracijaGesloDom"> Geslo </label>
                 <input type = "registracijaGesloDom1" class = "form-control" id = "exampleRegistracijaGesloDom1" aria-describedby="registracijaGesloDomHelp" placeholder="Geslo">
            </div>
            <button id="btnRegistracijaDom" type="submit">Registracija</button>
        </form>
        <br>
         <form action = "/">
            <button id="btnNazaj4" type="submit">Nazaj</button>
        </form>
    </div>
  </div>
</template>