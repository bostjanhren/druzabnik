<template>
    <div class = "loginDomovi">

        <div class = "topbar"></div>

        <div class = "underbar"> 

            <label class= "prijavaDom">Že imate račun?</label>
            <label class= "prijavaDom1">VPIS</label>

            <form action = "/domacastrandom">
                <div class="E-mail">
                    <input type="email" id="exampleInputEmail1" aria-describedby="emailHelp" placeholder=" Uporabniško ime">
                </div>
                <div class="Geslo">
                    <input type="password" id="exampleInputPassword1" placeholder=" Geslo">
                </div>
                <button id="btnPrijava" type="submit">Nadaljuj</button>
            </form>
            <br>
            <label class= "registracija-text">Še nimate računa?</label>
            <form action = "/registracijadom">
                <button id="btnRegistracija" type="submit">Registracija</button>
            </form>
        </div>
        <div style="clear: both;"></div>
    </div>
</template>