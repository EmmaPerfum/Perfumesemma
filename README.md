# Perfumesemma
index.html
<h1>Hola</h1>
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Emmañuel Perfumes</title>

    <style>
        *{
            margin:0;
            padding:0;
            box-sizing:border-box;
            font-family:Arial, Helvetica, sans-serif;
        }

        body{
            background:#111;
            color:white;
        }

        header{
            background:#000;
            text-align:center;
            padding:30px;
        }

        header img{
            width:180px;
            border-radius:15px;
        }

        h1{
            margin-top:15px;
            font-size:35px;
        }

        .buscador{
            display:flex;
            justify-content:center;
            margin:30px;
        }

        input{
            width:90%;
            max-width:500px;
            padding:15px;
            border:none;
            border-radius:10px;
            font-size:18px;
        }

        .catalogo{
            display:grid;
            grid-template-columns:repeat(auto-fit,minmax(260px,1fr));
            gap:25px;
            padding:30px;
        }

        .card{
            background:#1b1b1b;
            border-radius:15px;
            overflow:hidden;
            text-align:center;
            transition:.3s;
        }

        .card:hover{
            transform:scale(1.03);
        }

        .card img{
            width:100%;
            height:300px;
            object-fit:cover;
        }

        .card h2{
            margin:15px;
        }

        .precio{
            font-size:24px;
            color:#00ff95;
            margin-bottom:10px;
        }

        button{
            margin:15px;
            padding:12px 25px;
            border:none;
            border-radius:10px;
            background:white;
            color:black;
            cursor:pointer;
            font-size:16px;
        }

        .agotado{
            background:#555;
            color:white;
        }

        footer{
            text-align:center;
            padding:30px;
            background:#000;
            margin-top:30px;
        }
    </style>
</head>

<body>

<header>

<h1>Emmañuel Perfumes</h1>
<p>Perfumes originales al mejor precio.</p>

</header>

<div class="buscador">
<input type="text" id="buscar" placeholder="Buscar perfume...">
</div>

<div class="catalogo" id="catalogo">

</div>

<footer>

Entrega en punto acordado por WhatsApp.

</footer>

<script>

const perfumes = [

{
nombre:"Cherry Baby Sabrina",
precio:"800 MXN",
imagen:"https://images.unsplash.com/photo-1541643600914-78b084683601?w=800",
link:"https://wa.me/526695056778?text=Hola,%20me%20interesa%20el%20Cherry%20Baby%20Sabrina."
},

{
nombre:"9PM Night Out",
precio:"1200 MXN",
imagen:"https://images.unsplash.com/photo-1594035910387-fea47794261f?w=800",
link:"https://wa.me/526695056778?text=Hola,%20me%20interesa%20el%209PM%20Night%20Out."
},

{
nombre:"Set Lattafa Khamrah",
precio:"850 MXN",
imagen:"https://images.unsplash.com/photo-1615634260167-c8cdede054de?w=800",
link:"https://wa.me/526695056778?text=Hola,%20me%20interesa%20el%20Set%20Lattafa%20Khamrah."
},

{
nombre:"Odyssey Mandarin Sky",
precio:"AGOTADO",
imagen:"https://images.unsplash.com/photo-1523293182086-7651a899d37f?w=800",
agotado:true
}

];

const catalogo=document.getElementById("catalogo");

function mostrar(lista){

catalogo.innerHTML="";

lista.forEach(p=>{

catalogo.innerHTML+=`
<div class="card">

<img src="${p.imagen}">

<h2>${p.nombre}</h2>

<div class="precio">${p.precio}</div>

${p.agotado
?'<button class="agotado">AGOTADO</button>'
:`<button onclick="window.open('${p.link}')">Comprar por WhatsApp</button>`}

</div>
`;

});

}

mostrar(perfumes);

document.getElementById("buscar").addEventListener("input",e=>{

const texto=e.target.value.toLowerCase();

mostrar(perfumes.filter(p=>p.nombre.toLowerCase().includes(texto)));

});

</script>

</body>
</html>
