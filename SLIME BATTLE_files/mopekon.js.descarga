//const { application } = require("express")

//Bienvenida
let name = ""
name = prompt("Cual es tu nombre?")
alert("Bienvenido " + name)

//IniciarJuego
const seccionAtaque = document.getElementById("seleccionar-ataque")
const OcultarReinicio = document.getElementById("boton-reinicio")
const botonMascotaJugador = document.getElementById('boton-mascota')
const botonReinicio = document.getElementById("boton-reinicio")
const contenedorTarjetas = document.getElementById("Contenedor-Tarjetas")
//seleccionarMascotaJugador
const spanMascotaJugador = document.getElementById('mascota-jugador')
const seccionMascota = document.getElementById("seleccionar-mascota")  
const Imagen = new Image (80);
const MascotaIMG = document.querySelector("#Ataques-Jugador").appendChild(Imagen);
//seleccionarMascotaEnemigo
const EImagen = new Image (80);
const EMascotaIMG = document.querySelector("#Ataques-Enemigo").appendChild(EImagen);
//Combate
const spanVidasMascota = document.getElementById("vidas-mascota")
const spanVidasEnemigo = document.getElementById("vidas-enemigo")
const contenedorAtaques = document.getElementById("contenedor-Ataques")
//CrearMensaje
const sectionMensajes = document.getElementById('Resultado')
const AtaquesJugador = document.getElementById('Ataques-Jugador')
const AtaquesEnemigo = document.getElementById('Ataques-Enemigo')
//Mapa
const seccionMapa = document.getElementById("MAPA")
const nuestroMapa = document.getElementById("BUSCA")
const Botn = document.getElementById("Movimiento")
const Imapa = new Image ();
Imapa.src = "./Material/Mapa.jpg"
const MaxACH = 800

let jugadorid = null
let Slimes = []
let ataqueEnemigo = []
let ataqueJugador = []
let indexAtaqueJugador
let indexAtaqueEnemigo
let mascotaJugador
let mascotaJugadorObj
let ImagenFuego = new Image()
let ImagenCharco = new Image()
let ImagenMaraña = new Image()
let ImagenDorado = new Image()
let ataquesSlime
let ataquesSlimeEnemigo
let botonFuego 
let botonAgua 
let botonTierra 
let botonGOLD
let botonesA = []
let OpcionDeSlimes
let inputFuego 
let inputCharco 
let inputMaraña 
let inputDorado
let VictoriasJugador = 0
let VictoriasEnemigo = 0
let resultadoFinal
let Fondito = document.getElementById("Movimiento")
let Lienzo = nuestroMapa.getContext("2d")
let intervalo 
let ALTMapa
let ACHMapa = window.innerWidth - 20
ALTMapa = ACHMapa * 800 / 1600
if (ACHMapa > MaxACH) {
    ACHMapa = MaxACH - 20
    ALTMapa = 400
}
nuestroMapa.width = ACHMapa
nuestroMapa.height = ALTMapa

class Slime {
    constructor(nombre, foto, vida, fotomapa){
        this.nombre = nombre
        this.foto = foto
        this.vida = vida
        this.ataques = []
        this.ancho = ACHMapa * 40 / 400
        this.alto = ALTMapa * 40 / 200
        this.x = aleatorio(0, nuestroMapa.width - this.ancho)
        this.y = aleatorio(0, nuestroMapa.height - this.alto)
        this.velocidadX = 0
        this.velocidadY = 0
        this.mapaFoto = new Image()
        this.mapaFoto.src = foto
    }
    pintarSlime(){
        Lienzo.drawImage(
            this.mapaFoto,
            this.x,
            this.y,
            this.ancho,
            this.alto 
        )
    }
}

let Fuego = new Slime("Fuego", "./Material/Fuego.jpeg", 3) 
let Charco = new Slime("Charco", "./Material/Charco.jpeg", 3) 
let Maraña = new Slime("Maraña", "./Material/Maraña.jpeg", 3) 
let Dorado = new Slime("Dorado", "./Material/Gold_Slime.jpeg", 6) 
let FuegoE = new Slime("Fuego", "./Material/EI.png", 3) 
let CharcoE = new Slime("Charco", "./Material/EI.png", 3) 
let MarañaE = new Slime("Maraña", "./Material/EI.png", 3) 
let DoradoE = new Slime("Dorado", "./Material/EI.png", 6) 

Fuego.ataques.push(
    {nombre: "FUEGO", id: "boton-fuego"},
    {nombre: "AGUA", id: "boton-agua"},
    {nombre: "FUEGO", id: "boton-fuego"},
    {nombre: "TIERRA", id: "boton-tierra"},
    {nombre: "FUEGO", id: "boton-fuego"}
)
Charco.ataques.push(
    {nombre: "AGUA", id: "boton-agua"},
    {nombre: "FUEGO", id: "boton-fuego"},
    {nombre: "AGUA", id: "boton-agua"},
    {nombre: "TIERRA", id: "boton-tierra"},
    {nombre: "AGUA", id: "boton-agua"}
)
Maraña.ataques.push(
    {nombre: "TIERRA", id: "boton-tierra"},
    {nombre: "AGUA", id: "boton-agua"},
    {nombre: "TIERRA", id: "boton-tierra"},
    {nombre: "FUEGO", id: "boton-fuego"},
    {nombre: "TIERRA", id: "boton-tierra"}
)
Dorado.ataques.push(
    {nombre: "ORO", id: "boton-dorado"},
    {nombre: "AGUA", id: "boton-agua"},
    {nombre: "FUEGO", id: "boton-fuego"},
    {nombre: "TIERRA", id: "boton-tierra"},
    {nombre: "AGUA", id: "boton-agua"}
)  
FuegoE.ataques.push(
    {nombre: "FUEGO", id: "boton-fuego"},
    {nombre: "AGUA", id: "boton-agua"},
    {nombre: "FUEGO", id: "boton-fuego"},
    {nombre: "TIERRA", id: "boton-tierra"},
    {nombre: "FUEGO", id: "boton-fuego"}
)
CharcoE.ataques.push(
    {nombre: "AGUA", id: "boton-agua"},
    {nombre: "FUEGO", id: "boton-fuego"},
    {nombre: "AGUA", id: "boton-agua"},
    {nombre: "TIERRA", id: "boton-tierra"},
    {nombre: "AGUA", id: "boton-agua"}
)
MarañaE.ataques.push(
    {nombre: "TIERRA", id: "boton-tierra"},
    {nombre: "AGUA", id: "boton-agua"},
    {nombre: "TIERRA", id: "boton-tierra"},
    {nombre: "FUEGO", id: "boton-fuego"},
    {nombre: "TIERRA", id: "boton-tierra"}
)
DoradoE.ataques.push(
    {nombre: "ORO", id: "boton-dorado"},
    {nombre: "AGUA", id: "boton-agua"},
    {nombre: "FUEGO", id: "boton-fuego"},
    {nombre: "TIERRA", id: "boton-tierra"},
    {nombre: "AGUA", id: "boton-agua"}
)      
Slimes.push(Fuego, Charco, Maraña, Dorado)

function iniciarJuego() {
//ocultar 
    seccionAtaque.style.display = "none"
    seccionMapa.style.display = "none"
//Slimes
    Slimes.forEach((slime) => {
        OpcionDeSlimes = `
        <input type="radio" name="mascota" id=${slime.nombre} />
        <label class="tarjetaSlime" for=${slime.nombre}>
            <p><strong>${slime.nombre}</strong></p>
            <img src=${slime.foto} alt=${slime.nombre}>
        </label>
        `
    contenedorTarjetas.innerHTML += OpcionDeSlimes
        inputFuego = document.getElementById('Fuego')
        inputCharco = document.getElementById('Charco')
        inputMaraña = document.getElementById('Maraña')
        inputDorado = document.getElementById("Dorado")
    })
//Ocultar Reinicio
    OcultarReinicio.style.display = "none"
//Mascota
    botonMascotaJugador.addEventListener('click', seleccionarMascotaJugador)
//reinicio
    botonReinicio.addEventListener("click", reiniciarJuego)
//id
    unirseAlJuego()
}
function unirseAlJuego() {
    fetch("http://localhost:8080/unirse")
    .then(function (res){
        if (res.ok) {
            res.text()
            .then(function(respuesta){
                console.log(respuesta)
                jugadorid = respuesta
            })
        }
    })
}
function seleccionarMascotaJugador() {
    //deshabilitar boton
    botonMascotaJugador.disabled = true
    //ocultar Mascota
    seccionMascota.style.display = "none"
    if (inputFuego.checked) {
        var MascotaIMG
        Imagen.src = "./Material/Fuego.jpeg";
        mascotaJugador = inputFuego.id
    } else if (inputCharco.checked) {
        var MascotaIMG
        Imagen.src = "./Material/Charco.jpeg";
        mascotaJugador = inputCharco.id
    } else if (inputMaraña.checked) {
        var MascotaIMG
        Imagen.src = "./Material/Maraña.jpeg";
        mascotaJugador = inputMaraña.id
    } else if (inputDorado.checked) {
        var MascotaIMG
        Imagen.src = "./Material/Gold_Slime.jpeg"
        mascotaJugador = inputDorado.id
    } else  {
        alert("No ha seleccionado tu slime")
        reiniciarJuego()
    }
    seleccionarSlime(mascotaJugador)
    extaerAtaques(mascotaJugador)
    seccionMapa.style.display = "flex"
    Botn.style.display = "flex"
    IniciarMapa()
}
function seleccionarSlime(mascotaJugador) {
    fetch(`http://localhost:8080/slime/${jugadorid}`,{
        method: "post",
        headers: {
            "Content-Type": "application/json"
        }, body: JSON.stringify({
            slime: mascotaJugador
        })
    });
}
function pintarCanvas(){
    mascotaJugadorObj.x = mascotaJugadorObj.x + mascotaJugadorObj.velocidadX
    mascotaJugadorObj.y = mascotaJugadorObj.y + mascotaJugadorObj.velocidadY
    Lienzo.clearRect(0, 0, nuestroMapa.width, nuestroMapa.height)
    Lienzo.drawImage(
        Imapa,
        0,
        0,
        nuestroMapa.width,
        nuestroMapa.height
    )
    mascotaJugadorObj.pintarSlime()
    enviarPosicion(mascotaJugadorObj.x, mascotaJugadorObj.y)
    FuegoE.pintarSlime()
    CharcoE.pintarSlime()
    MarañaE.pintarSlime()
    DoradoE.pintarSlime()
    if (mascotaJugadorObj.velocidadX !== 0 || mascotaJugadorObj.velocidadY !== 0) {
        revisarColision(FuegoE)
        revisarColision(CharcoE)
        revisarColision(MarañaE)
        revisarColision(DoradoE)
    }
}
function enviarPosicion(x, y) {
    fetch(`http://localhost:8080/slime/${jugadorid}/posicion`,{
        method: "post",
        headers: {"Content-Type": "application"},
        body: JSON.stringify({x, y})
    })
    .then(function(res){
        if (res.ok){
            res.json()
            .then(function({enemigos}){
                console.log(enemigos)
            })
        }
    })
}
function SlimeM(){
    for (let i = 0; i < Slimes.length; i++) {
        if (mascotaJugador === Slimes[i].nombre) {
            return Slimes[i]
        }
    }
}
function moverSlimeD(){
    mascotaJugadorObj.velocidadX = 5
}
function moverSlimeI(){
    mascotaJugadorObj.velocidadX = -5 
}
function moverSlimeA(){
    mascotaJugadorObj.velocidadY = 5 
}
function moverSlimeAB(){
    mascotaJugadorObj.velocidadY = -5 

}
function Teclas(event){
    console.log(event.key)
    switch (event.key) {
        case "w":
            moverSlimeAB()
            break;
        case "ArrowUp":
            moverSlimeAB()
            break;
        case "s":
            moverSlimeA()
            break;
        case "ArrowDown":
            moverSlimeA()
            break;
        case "a":
            moverSlimeI()
            break;
        case "ArrowLeft":
            moverSlimeI()
            break;
        case "d":
            moverSlimeD()
            break; 
        case "ArrowRight":
            moverSlimeD()   
            break;           
        default:
            break;
    }
}
function detenerSlime(){
    mascotaJugadorObj.velocidadX = 0
    mascotaJugadorObj.velocidadY = 0
}

function extaerAtaques(){
    let ataques
    for (let i = 0; i < Slimes.length; i++) {
        if (mascotaJugador === Slimes[i].nombre) {
            ataques = Slimes[i].ataques
        }
    }
    mostrarAtaques(ataques)
}

function mostrarAtaques(ataques){
    ataques.forEach((ataque) => {
        ataquesSlime = `
        <button id=${ataque.id} class="Botones-de-Fuego BAtaque"><strong>${ataque.nombre}</strong></button>
        `
        contenedorAtaques.innerHTML += ataquesSlime
    })
    botonFuego = document.getElementById('boton-fuego')
    botonAgua = document.getElementById('boton-agua')
    botonTierra = document.getElementById('boton-tierra')
    botonGOLD = document.getElementById('boton-Dorado')
    botonesA = document.querySelectorAll(".BAtaque")
}

function secuenciaAtaque(){
    botonesA.forEach((boton) =>{
        boton.addEventListener("click", (e) => {
            if (e.target.textContent === "FUEGO"){
                ataqueJugador.push("FUEGO")
                console.log(ataqueJugador)
                boton.style.background = "#BBBFCA"
                boton.disabled = true
            }else if(e.target.textContent === "AGUA"){
                ataqueJugador.push("AGUA")
                console.log(ataqueJugador)
                boton.style.background = "#BBBFCA"
                boton.disabled = true
            }else if(e.target.textContent === "ORO"){
                ataqueJugador.push("ORO")
                console.log(ataqueJugador)
                boton.style.background = "#BBBFCA"
                boton.disabled = true
            }else {
                ataqueJugador.push("TIERRA")
                console.log(ataqueJugador)
                boton.style.background = "#BBBFCA" 
                boton.disabled = true
            }
            ataqueAleatorioEnemigo()
        })
    })
}

function seleccionarMascotaEnemigo(enemigo) {
    let mascotaAleatoria = aleatorio(0 ,Slimes.length -1)
    if (mascotaAleatoria == 0) {
        var EMascotaIMG
        EImagen.src = "./Material/Fuego.jpeg";
    } else if (mascotaAleatoria == 1) {
        var EMascotaIMG
        EImagen.src = "./Material/Charco.jpeg";
    } else if (mascotaAleatoria == 2){
        var EMascotaIMG
        EImagen.src = "./Material/Maraña.jpeg";
    }else {
        var EMascotaIMG
        EImagen.src = "./Material/Gold_Slime.jpeg";
    }
    ataquesSlimeEnemigo = enemigo.ataques
    secuenciaAtaque()
}

function ataqueAleatorioEnemigo() {
    let ataqueAleatorio = aleatorio(0 ,ataquesSlimeEnemigo.length)

    if (ataqueAleatorio == 0 || ataqueAleatorio == 1) {
        ataqueEnemigo.push('FUEGO')
    } else if (ataqueAleatorio == 2 || ataqueAleatorio == 3) {
        ataqueEnemigo.push('AGUA')
    } else if (ataqueAleatorio == 3 || ataqueAleatorio == 4) {
        ataqueEnemigo.push('TIERRA')
    }else if (ataqueAleatorio == 5){
        ataqueEnemigo.push('AGUA')
    }else if (mascotaAleatoria == 4 && ataqueAleatorio == 5) {
        ataqueEnemigo.push('ORO') 
    }
    console.log(ataqueEnemigo)
    inciarPelea()
}

function inciarPelea(){
    if (ataqueJugador.length === 5) {
        combate()
    }
}

function indexAmbosOponentes(jugador, enemigo){
    indexAtaqueJugador = ataqueJugador[jugador]
    indexAtaqueEnemigo = ataqueEnemigo[enemigo]
}

function combate() {
    for (let index = 0; index < ataqueJugador.length; index++) {
        if (ataqueJugador[index] === ataqueEnemigo[index]) {
            indexAmbosOponentes(index, index)
            crearMensaje("VAYA, SON IGUALES!")
        }else if (ataqueJugador[index] ==="FUEGO" && ataqueEnemigo[index] === "TIERRA") {
            indexAmbosOponentes(index, index)
            crearMensaje("BIEN HECHO, QUE SE HAGA EL FUEGO!")
            VictoriasJugador++
            spanVidasMascota.innerHTML = VictoriasJugador
        }else if (ataqueJugador[index] ==="FUEGO" && ataqueEnemigo[index] === "ORO") {
            indexAmbosOponentes(index, index)
            crearMensaje("BIEN HECHO, QUE SE HAGA EL FUEGO!")
            VictoriasJugador++
            spanVidasMascota.innerHTML = VictoriasJugador
        }else if (ataqueJugador[index] ==="AGUA" && ataqueEnemigo[index] === "FUEGO") {
            indexAmbosOponentes(index, index)
            crearMensaje("EXCELENTE, SU LLAMA NO TE AFECTA!")
            VictoriasJugador++
            spanVidasMascota.innerHTML = VictoriasJugador
        }else if (ataqueJugador[index] ==="TIERRA" && ataqueEnemigo[index] === "AGUA") {
            indexAmbosOponentes(index, index)
            crearMensaje("VAMOS, EL NO PASARA!")
            VictoriasJugador++
            spanVidasMascota.innerHTML = VictoriasJugador
        }else if (ataqueJugador[index] ==="ORO" && ataqueEnemigo[index] === "AGUA") {
            indexAmbosOponentes(index, index)
            crearMensaje("INCREIBLE!, TAN BRILLANTE!")
            VictoriasJugador++
            spanVidasMascota.innerHTML = VictoriasJugador
        }else if (ataqueJugador[index] ==="ORO" && ataqueEnemigo[index] === "TIERRA") {
            indexAmbosOponentes(index, index)
            crearMensaje("INCREIBLE!, TAN BRILLANTE!")
            VictoriasJugador++
            spanVidasMascota.innerHTML = VictoriasJugador
        }else {
            indexAmbosOponentes(index, index)
            crearMensaje("OH NO, TU ENEMIGO TE VENCIO!")
            VictoriasEnemigo++
            spanVidasEnemigo.innerHTML = VictoriasEnemigo
        }
    }
    revisarTablas()
}

function revisarTablas() {
    if (VictoriasJugador == VictoriasEnemigo){
        crearMensajeFinal("ESTO FUE ALGO INESPERADO, EMPATE")
    }else if (VictoriasJugador > VictoriasEnemigo){
        crearMensajeFinal("PERFECTO, ERES MUY FUERTE!")
    }else {
        crearMensajeFinal("YA LO SUPONIA, ERES DEBIL!")
    }
}

function crearMensaje(resultado) {
 
    let NuevoAtaqueJugador = document.createElement('p')
    let NuevoAtaqueEnemigo = document.createElement('p')

    sectionMensajes.innerHTML = resultado
    NuevoAtaqueJugador.innerHTML = indexAtaqueJugador
    NuevoAtaqueEnemigo.innerHTML = indexAtaqueEnemigo

    AtaquesJugador.appendChild(NuevoAtaqueJugador)
    AtaquesEnemigo.appendChild(NuevoAtaqueEnemigo)
}

function crearMensajeFinal(resultadoFinal) {
    OcultarReinicio.style.display = "block"
    sectionMensajes.innerHTML = resultadoFinal
}

function reiniciarJuego(){
    location.reload()
}

function aleatorio(min, max) {
    return Math.floor(Math.random() * (max - min + 1) + min)
}
function IniciarMapa(){
    mascotaJugadorObj = SlimeM(mascotaJugador)
    intervalo = setInterval(pintarCanvas, 50)
    window.addEventListener('keydown', Teclas)
    window.addEventListener("keyup", detenerSlime)
}
function revisarColision(enemigo){
    const arribaE = enemigo.y + 25
    const abajoE = enemigo.y + enemigo.alto - 25
    const derechaE = enemigo.x + enemigo.ancho - 25
    const izquierdaE = enemigo.x + 25
    const arribaJ = mascotaJugadorObj.y
    const abajoJ = mascotaJugadorObj.y + mascotaJugadorObj.alto
    const derechaJ = mascotaJugadorObj.x + mascotaJugadorObj.ancho
    const izquierdaJ = mascotaJugadorObj.x 

    if (abajoJ<arribaE || arribaJ > abajoE || derechaJ < izquierdaE || izquierdaJ > derechaE) {
        return 
    }
    detenerSlime()
    clearInterval(intervalo)
    console.log("Se detecto una colision")
    seccionAtaque.style.display = "flex"
    seccionMapa.style.display = "none"
    Botn.style.display = "none"
    seleccionarMascotaEnemigo(enemigo)
}
window.addEventListener('load', iniciarJuego)