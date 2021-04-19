<template>
<div>
    <form action = "/domacastrandom">
        <div class="form-group">
            <label for="exampleInputEmail1">E-poštni naslov</label>
            <input type="email" class="form-control" id="exampleInputEmail1" aria-describedby="emailHelp" placeholder="Vnesi email">
        </div>
        <div class="form-group">
            <label for="exampleInputPassword1">Geslo</label>
            <input type="password" class="form-control" id="exampleInputPassword1" placeholder="Password">
        </div>
        <button type="submit" class="btn btn-primary">Prijava</button>
    </form>
    <br>
    <form action = "/registracijadom">
        <button type="submit" class="btn btn-primary">Registracija</button>
    </form>
</div>
</template>