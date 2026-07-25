index.html
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Emmañuel Perfumes</title>

<link rel="stylesheet" href="style.css">

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap" rel="stylesheet">

</head>

<body>

<header>

<div class="logo">
<h1>Emmañuel Perfumes</h1>
<p>Perfumes originales • Compra por WhatsApp</p>
</div>

</header>

<section class="hero">

<h2>Encuentra tu próximo perfume</h2>

<p>Originales • Excelente calidad • Entrega en punto acordado</p>

<input type="text" id="buscador" placeholder="Buscar perfume...">

</section>

<section id="catalogo" class="catalogo">

</section>

<footer>

<p>📍 Entrega en punto acordado.</p>

<p>© Emmañuel Perfumes</p>

</footer>

<script src="script.js"></script>

</body>
</html>
style.css
*{
margin:0;
padding:0;
box-sizing:border-box;
font-family:'Poppins',sans-serif;
}

body{
background:#0f0f0f;
color:white;
}

header{
background:#000;
padding:25px;
text-align:center;
border-bottom:1px solid #333;
}

.logo h1{
font-size:2rem;
}

.logo p{
color:#bdbdbd;
margin-top:8px;
}

.hero{
padding:50px 20px;
text-align:center;
}

.hero h2{
font-size:2.3rem;
margin-bottom:10px;
}

.hero p{
color:#bfbfbf;
margin-bottom:25px;
}

#buscador{
width:90%;
max-width:500px;
padding:15px;
border:none;
border-radius:12px;
font-size:16px;
outline:none;
}

.catalogo{
display:grid;
grid-template-columns:repeat(auto-fit,minmax(270px,1fr));
gap:25px;
padding:40px 20px;
}

.card{
background:#1b1b1b;
border-radius:18px;
overflow:hidden;
transition:.3s;
box-shadow:0 10px 25px rgba(0,0,0,.35);
}

.card:hover{
transform:translateY(-8px);
}

.card img{
width:100%;
height:320px;
object-fit:cover;
}

.info{
padding:20px;
}

.info h3{
margin-bottom:10px;
}

.precio{
font-size:22px;
font-weight:700;
margin-bottom:15px;
}

button{
width:100%;
padding:14px;
background:white;
color:black;
border:none;
border-radius:10px;
font-weight:600;
cursor:pointer;
}

button:hover{
background:#d9d9d9;
}

.agotado{
background:#555;
color:white;
cursor:not-allowed;
}

footer{
background:#000;
text-align:center;
padding:30px;
color:#bdbdbd;
margin-top:30px;
}
script.js
const perfumes = [
{
nombre:"Cherry Baby Sabrina",
precio:"$800 MXN",
imagen:"https://images.openai.com/thumbnails/url/cherry-baby-sabrina.jpg",
whatsapp:"Cherry Baby Sabrina"
},
{
nombre:"9PM Night Out",
precio:"$1200 MXN",
imagen:"https://images.openai.com/thumbnails/url/9pm-night-out.jpg",
whatsapp:"9PM Night Out"
},
{
nombre:"Set Lattafa Khamrah",
precio:"$850 MXN",
imagen:"https://images.openai.com/thumbnails/url/lattafa-khamrah-set.jpg",
whatsapp:"Set Lattafa Khamrah"
},
{
nombre:"Odyssey Mandarin Sky",
precio:"AGOTADO",
imagen:"https://images.openai.com/thumbnails/url/odyssey-mandarin-sky.jpg",
agotado:true
}
];

const catalogo=document.getElementById("catalogo");

function mostrar(lista){

catalogo.innerHTML="";

lista.forEach(p=>{

catalogo.innerHTML+=`
<div class="card">

<img src="${p.imagen}" alt="${p.nombre}">

<div class="info">

<h3>${p.nombre}</h3>

<div class="precio
