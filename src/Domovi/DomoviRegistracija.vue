<template>
  <div class = "registrationPageDomove">
    <div class = "topbar"></div>
    <div class = "underbar">
        <label class = "registracijaDom">REGISTRACIJA</label>
        <form>
            <!-- ime doma upokojencev -->
            <div class = "registacijaImeDom">
                 <input type = "registracijaImeDom1" id = "exampleRegistracijaImeDom1" aria-describedby="registracijaImeDomHelp" placeholder=" Uporabniško ime">
            </div>

           <!--E-postni naslov doma upokojencev -->
            <div class = "registracijaPostniNaslovDom">
                 <input type = "registracijaPostniNaslovDom1" id = "exampleRegistracijaPostniNaslovDom1" aria-describedby="registracijaPostniNaslovDomHelp" placeholder=" e-naslov">
            </div>

            <!--geslo doma upokojencev -->
            <div class = "registracijaGesloDom">
                 <input type = "registracijaGesloDom1" id = "exampleRegistracijaGesloDom1" aria-describedby="registracijaGesloDomHelp" placeholder=" Geslo">
            </div>
             <label class = "pogojiUporabe">S klikom gumba "Nadaljuj" se uporabnik strinja s pogoji uporabe.</label>
            <button id="btnRegistracijaDom" type="submit">Nadaljuj</button>
        </form>
    </div>
  </div>
</template>