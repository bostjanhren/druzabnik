<template>
    <div class = "loginDomovi">

        <div class = "topbar"></div>

        <div class = "underbar"> 

            <form action = "/domacastrandom">
                <div class="E-mail">
                    <label class= "email-text" for="exampleInputEmail1">E-poštni naslov</label>
                    <input type="email" class="form-control" id="exampleInputEmail1" aria-describedby="emailHelp" placeholder="Vnesi email">
                </div>
                <div class="Geslo">
                    <label class= "geslo-text" for="exampleInputPassword1">Geslo</label>
                    <input type="password" class="form-control" id="exampleInputPassword1" placeholder="Geslo">
                </div>
                <button id="btnPrijava" type="submit">Prijava</button>
            </form>
            <br>
            <form action = "/registracijadom">
                <label class= "registracija-text" for="exampleInputPassword1">Ali še niste uporabnik?</label>
                <button id="btnRegistracija" type="submit">Registracija</button>
            </form>
            <form action = "/">
                <button id="btnNazaj" type="submit">Nazaj</button>
            </form>
        </div>
    </div>
</template>