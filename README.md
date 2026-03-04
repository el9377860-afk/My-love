<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Feliz Cumpleaños ❤️</title>

<style>

body{
    margin:0;
    font-family: Arial, sans-serif;
    text-align:center;
    background: linear-gradient(135deg,#ff9a9e,#fad0c4);
    overflow-x:hidden;
    overflow-y:auto;
}

/* ===== PORTADA ===== */
#portada{
    position:fixed;
    width:100%;
    height:100vh;
    background:linear-gradient(135deg,#ff9a9e,#fad0c4);
    display:flex;
    flex-direction:column;
    justify-content:center;
    align-items:center;
    z-index:999;
}

#portada img{
    width:260px;
    height:260px;
    object-fit:cover;
    border-radius:20px;
    box-shadow:0 0 25px rgba(0,0,0,0.3);
    margin-bottom:20px;
}

.frasePortada{
    color:white;
    max-width:85%;
    font-size:18px;
    margin-bottom:25px;
    line-height:1.6;
    text-shadow:0 0 10px rgba(0,0,0,0.4);
}

#abrirBtn{
    background:#ff4d6d;
    border:none;
    color:white;
    padding:18px 30px;
    font-size:20px;
    border-radius:20px;
    cursor:pointer;
    animation:latir 1.2s infinite;
}

@keyframes latir{
    0%{transform:scale(1);}
    50%{transform:scale(1.08);}
    100%{transform:scale(1);}
}

/* CONTENIDO */
#contenido{
    display:none;
}

.cumple{
    background:white;
    margin:20px;
    padding:25px;
    border-radius:20px;
    box-shadow:0 0 25px rgba(0,0,0,0.2);
}

h1{ color:#ff3366; }

button{
    background:#ff4d6d;
    border:none;
    color:white;
    padding:15px 25px;
    margin:15px;
    font-size:18px;
    border-radius:15px;
    cursor:pointer;
}

/* MENSAJE FINAL */
#mensajeFinal{
    display:none;
    background:white;
    margin:25px;
    padding:25px;
    border-radius:20px;
    box-shadow:0 0 20px rgba(0,0,0,0.2);
    font-size:20px;
    line-height:1.7;
    white-space:pre-line;
}

/* ESTRELLAS */
.estrella{
    position:fixed;
    color:white;
    font-size:10px;
    animation:brillar 3s infinite alternate;
}

@keyframes brillar{
    from{opacity:0.3;}
    to{opacity:1; transform:scale(1.5);}
}

/* PETALOS */
.petalo{
    position:fixed;
    top:-20px;
    font-size:24px;
    animation:caer linear forwards;
}

@keyframes caer{
    to{
        transform:translateY(100vh) rotate(360deg);
        opacity:0;
    }
}

</style>
</head>

<body>

<!-- ===== PORTADA ===== -->
<div id="portada">

<img src="portada.jpg" alt="Nuestra foto ❤️">

<p class="frasePortada">
💌 Mi foto favorita ya que es la que expresa tu felicidad que también me pone feliz a mi y la sonrisa mas linda que he visto, sin lugar a duda la que me enamora 💗
</p>

<button id="abrirBtn" onclick="abrirRegalo()">
🎁 Abrir mi regalo
</button>

</div>

<!-- ===== CONTENIDO ===== -->
<div id="contenido">

<div class="cumple">
<h1>❤️‍🩹💌 ¡Feliz Cumpleaños! 💌❤️‍🩹</h1>

<p>
Que Dios te bendiga hoy y siempre 🤍.<br><br>
Le agradezco mucho a Dios por tu existencia,
eres la niña más linda que existe recuerda que siempre estare contigo para apoyarte y nunca dudes de ti por que Dios siempre estara a tu lado 🌸.
</p>

<button onclick="mostrarMensaje()">💗 Presiona aquí</button>
</div>

<div id="mensajeFinal"></div>

</div>

<script>

/* ABRIR REGALO */
function abrirRegalo(){
    document.getElementById("portada").style.display="none";
    document.getElementById("contenido").style.display="block";
}

/* ESTRELLAS */
for(let i=0;i<40;i++){
    let e=document.createElement("div");
    e.className="estrella";
    e.innerText="✨";
    e.style.left=Math.random()*100+"vw";
    e.style.top=Math.random()*100+"vh";
    document.body.appendChild(e);
}

/* FRASE */
const texto = `Mi niña bonita, chaparrita de ojitos tan hermosos que todavía me ponen nervioso cada vez que me miras… no sé qué tienen, pero hacen que mi corazón lata más rápido y al mismo tiempo me hacen sentir una paz muy linda cuando estoy contigo. Te amo con todo mi corazón, y más que momentos contigo, quiero un futuro lleno de abrazos, risas y muchos besitos, porque a tu lado entendí que el amor más bonito es el que se siente contigo 💗 Esto mas que un feliz cumpleaños es una muestra de que tal vez te vi cuando tenias 13 te hable cuando tenias 14 pero te amo desde tus 15 y desde ese momento hasta el fin del planeta me tendrás a tu lado esperándote y que solo quiero ser feliz contigo ❤️‍🩹`;

/* MOSTRAR MENSAJE */
function mostrarMensaje(){

    crearPetalos();

    let caja=document.getElementById("mensajeFinal");
    caja.style.display="block";
    caja.innerHTML="";

    caja.scrollIntoView({behavior:"smooth"});

    let i=0;
    function escribir(){
        if(i<texto.length){
            caja.innerHTML+=texto.charAt(i);
            i++;
            setTimeout(escribir,30);
        }
    }
    escribir();
}

/* PETALOS */
function crearPetalos(){
    for(let i=0;i<40;i++){
        let p=document.createElement("div");
        p.className="petalo";
        p.innerText="🌹";
        p.style.left=Math.random()*100+"vw";
        p.style.animationDuration=(3+Math.random()*3)+"s";
        document.body.appendChild(p);

        setTimeout(()=>p.remove(),6000);
    }
}

</script>

</body>
</html>
