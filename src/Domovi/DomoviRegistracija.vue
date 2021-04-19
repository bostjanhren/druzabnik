
<template>
<div>
    <label for="address">Vnesite podatke vaše ustanove</label>
    <br>
    <form action = "/domacastrandom">
        <div class="form-group">
            <label for="exampleInputEmail1">E-poštni naslov</label>
            <input type="email" class="form-control" id="exampleInputEmail1" aria-describedby="emailHelp" placeholder="Vnesi email">
        </div>
        <div class="form-group">
            <label for="address">Naslov doma upokojencev</label>
            <input type="text" class="form-control" id="InputAddress" placeholder="Naslov ustanove">
        </div>
        <div class="form-group">
            <label for="exampleInputPassword1">Geslo</label>
            <input type="password" class="form-control" id="exampleInputPassword1" placeholder="Password">
        </div>
        <button type="submit" class="btn btn-primary">Registracija</button>
    </form>
</div>
</template>