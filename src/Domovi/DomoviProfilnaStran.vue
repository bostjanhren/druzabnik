<template>
    <div>
        <h1>Urejanje podatkov ustanove</h1>
        
        <br>
    <form action = "/domacastrandom">
        <div class="form-group">
            <label for="exampleInputEmail1">Dodaj telefonsko številko ustanove</label>
            <input type="tel" class="form-control" id="exampleInputEmail1" aria-describedby="emailHelp" placeholder="Telefonska številka">
        </div>
        <div class="form-group">
            <label for="address">Spremeni naslov ustanove</label>
            <input type="text" class="form-control" id="InputAddress" placeholder="Naslov ustanove">
        </div>
        <div class="form-group">
            <label for="exampleInputPassword1">Spremeni geslo</label>
            <input type="password" class="form-control" id="exampleInputPassword1" placeholder="Password">
        </div>
        <div class="form-group">
            <label for="exampleInputPassword1">Opis ustanove</label>
            <textarea class="form-control" aria-label="With textarea"></textarea>
        </div>
        <button type="submit" class="btn btn-primary">Posodobi podatke</button>
    </form>
    </div>
</template>