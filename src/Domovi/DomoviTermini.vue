<template>
    <div>
        <h1>Urejanje terminov za obsike</h1>
        
        <br>

    <div class="d-flex flex-row bd-highlight mb-3">
        <div class="p-2 bd-highlight">
            <div class="card" style="width: 18rem;">
                <div class="card-header">
                    Ponedeljek 26.04.2021
                </div>
                <ul class="list-group list-group-flush">
                    <li class="list-group-item">11-12</li>
                    <li class="list-group-item">12-13</li>
                    <li class="list-group-item">15-16</li>
                </ul>
            </div>
        </div>
        <div class="p-2 bd-highlight">
            <div class="card" style="width: 18rem;">
                <div class="card-header">
                    Torek 27.04.2021
                </div>
                <ul class="list-group list-group-flush">
                    <li class="list-group-item">11-12</li>
                    <li class="list-group-item">12-13</li>
                    <li class="list-group-item">15-16</li>
                </ul>
            </div>
        </div>
        
    </div>

    <form action="/domacastrandom">
        <button type="submit" class="btn btn-primary">Shrani spremembe</button>
    </form>
    
    <br>

    <form action="/novTermin">
        <button type="submit" class="btn btn-primary">Nov Termin</button>
    </form>

    </div>
</template>
