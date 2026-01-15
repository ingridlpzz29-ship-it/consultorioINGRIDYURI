# consultorioINGRIDYURI
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<title>Consultorio Nutricional Rosa Pastel</title>

<style>
html{
  scroll-behavior:smooth;
}

/* ===== FONDO GENERAL ===== */
body{
  margin:0;
  font-family:'Poppins', 'Segoe UI', Arial;
  background:linear-gradient(135deg,#fde2f3,#fce4ec);
}

/* ===== MENÚ SUPERIOR (BOTONES DIFERENTES) ===== */
nav{
  position:sticky;
  top:0;
  background:#fff0f6;
  padding:15px;
  display:flex;
  justify-content:center;
  gap:18px;
  box-shadow:0 4px 10px rgba(214,51,132,.25);
  z-index:1000;
}

nav a{
  text-decoration:none;
  color:#ad1457;
  font-weight:600;
  padding:10px 20px;
  border-radius:12px;
  background:linear-gradient(145deg,#ffd6e8,#f8bbd0);
  transition:all .3s ease;
}

nav a:hover{
  transform:translateY(-3px) scale(1.05);
  background:linear-gradient(145deg,#f48fb1,#f06292);
  color:white;
}

/* ===== HEADER ===== */
header{
  text-align:center;
  padding:35px;
  background:linear-gradient(160deg,#f8bbd0,#fce4ec);
  color:#880e4f;
}

header img{
  width:110px;
  margin:8px;
  border-radius:18px;
  box-shadow:0 5px 12px rgba(0,0,0,.2);
}

/* ===== SECCIONES ===== */
section{
  margin:35px;
  background:#fff;
  padding:30px;
  border-radius:30px;
  box-shadow:0 12px 25px rgba(214,51,132,.2);
}

h2{
  text-align:center;
  color:#ad1457;
  margin-bottom:20px;
}

/* ===== CONTENEDOR ===== */
.contenedor{
  display:flex;
  gap:30px;
  flex-wrap:wrap;
}

.formulario, .tabla{
  flex:1;
  min-width:320px;
}

/* ===== INPUTS ===== */
input, textarea{
  width:100%;
  padding:12px;
  margin:8px 0;
  border-radius:14px;
  border:2px solid #f8bbd0;
  outline:none;
  font-size:14px;
}

input:focus, textarea:focus{
  border-color:#ec407a;
  box-shadow:0 0 8px rgba(236,64,122,.4);
}

/* ===== BOTONES (TODOS DIFERENTES) ===== */
button{
  border:none;
  padding:12px;
  border-radius:30px;
  font-weight:700;
  letter-spacing:1px;
  cursor:pointer;
  transition:all .3s ease;
}

/* BOTÓN GUARDAR */
button.guardar{
  background:linear-gradient(135deg,#f48fb1,#ec407a);
  color:white;
}
button.guardar:hover{
  transform:scale(1.05);
  box-shadow:0 8px 15px rgba(236,64,122,.4);
}

/* BOTÓN EDITAR */
button.editar{
  background:linear-gradient(135deg,#fce4ec,#f8bbd0);
  color:#880e4f;
}
button.editar:hover{
  background:#f06292;
  color:white;
}

/* BOTÓN ELIMINAR */
button.eliminar{
  background:linear-gradient(135deg,#ff8a80,#ff5252);
  color:white;
}
button.eliminar:hover{
  transform:rotate(-2deg) scale(1.05);
}

/* BOTÓN PROPÓSITO */
button.proposito{
  background:linear-gradient(135deg,#ce93d8,#f48fb1);
  color:white;
}
button.proposito:hover{
  box-shadow:0 10px 20px rgba(206,147,216,.6);
}

/* ===== TABLAS ===== */
table{
  width:100%;
  border-collapse:collapse;
  border-radius:20px;
  overflow:hidden;
}

th{
  background:linear-gradient(135deg,#f8bbd0,#f48fb1);
  color:#6a1b4d;
  padding:12px;
}

td{
  padding:10px;
  border-bottom:1px solid #fce4ec;
  text-align:center;
}

tr:hover{
  background:#fff0f6;
}

/* TABLA MALA ALIMENTACIÓN */
.mala th{
  background:linear-gradient(135deg,#f06292,#e91e63);
  color:white;
}
</style>

</head>

<body>

<!-- ===== MENU ===== -->
<nav>
  <a href="#nutri">Nutricionistas</a>
  <a href="#ado">Adolescentes IMC</a>
  <a href="#info">Alimentación</a>
  <a href="#pro">Propósitos</a>
</nav>

<!-- ===== HEADER ===== -->
<header>
  <h1>Consultorio Nutricional</h1>
  <p><strong>Ingrid Geraldine González López</strong></p>
  <p><strong>Aylin Yuritzy de Jesús Flores</strong></p>


</header>

<!-- ===== NUTRICIONISTAS ===== -->
<section id="nutri">
<h2>Nutricionistas</h2>

<div class="contenedor">
  <div class="formulario">
    <input id="nid" placeholder="ID">
    <input id="nnombre" placeholder="Nombre">
    <input id="nedad" placeholder="Edad">
    <button onclick="guardarNutri()">Guardar</button>
  </div>

  <div class="tabla">
    <table>
      <thead>
        <tr><th>ID</th><th>Nombre</th><th>Edad</th><th>Acciones</th></tr>
      </thead>
      <tbody id="tablaNutri"></tbody>
    </table>
  </div>
</div>
</section>

<!-- ===== ADOLESCENTES ===== -->
<section id="ado">
<h2>Adolescentes (IMC)</h2>

<div class="contenedor">
  <div class="formulario">
    <input id="anombre" placeholder="Nombre">
    <input id="aedad" placeholder="Edad">
    <input id="altura" placeholder="Altura (m)">
    <input id="peso" placeholder="Peso (kg)">
    <button onclick="guardarAdo()">Calcular IMC</button>
  </div>

  <div class="tabla">
    <table>
      <thead>
        <tr>
          <th>Nombre</th><th>Edad</th><th>Altura</th><th>Peso</th>
          <th>IMC</th><th>Estado</th><th>Acciones</th>
        </tr>
      </thead>
      <tbody id="tablaAdo"></tbody>
    </table>
  </div>
</div>
</section>

<!-- ===== INFO ===== -->
<section id="info">
<h2>Alimentación Saludable</h2>

<table>
<tr>
  <th>Ventajas de una Buena Alimentación</th>
  <th>Frases Motivadoras</th>
</tr>
<tr>
  <td>
    ✔ Aumenta la energía diaria<br>
    ✔ Mejora la condición física<br>
    ✔ Fortalece el sistema inmunológico<br>
    ✔ Ayuda a mantener un peso saludable<br>
    ✔ Mejora la concentración y el rendimiento escolar<br>
    ✔ Reduce el riesgo de enfermedades<br>
    ✔ Mejora la autoestima y la imagen personal<br>
    ✔ Favorece el crecimiento y desarrollo adecuado
  </td>
  <td>
    "Tu cuerpo es reflejo de tu disciplina"<br>
    "Cada comida saludable cuenta"<br>
    "Cuidar tu alimentación es cuidar tu futuro"<br>
    "La salud es una decisión diaria"<br>
    "Lo que comes hoy define tu mañana"<br>
    "Un cuerpo sano empieza con buenos hábitos"
  </td>
</tr>
</table>

<br>

<table class="mala">
<tr>
  <th>Desventajas de una Mala Alimentación</th>
</tr>
<tr>
  <td>
    ❌ Sobrepeso y obesidad<br>
    ❌ Aparición de enfermedades crónicas (diabetes, hipertensión)<br>
    ❌ Bajo rendimiento físico y mental<br>
    ❌ Cansancio constante y falta de energía<br>
    ❌ Problemas digestivos<br>
    ❌ Baja autoestima y desmotivación<br>
    ❌ Deficiencia de vitaminas y minerales<br>
    ❌ Mayor riesgo de problemas del corazón
  </td>
</tr>
</table>

</section>

<!-- ===== PROPÓSITOS ===== -->
<section id="pro">
<h2>Mis Propósitos</h2>

<textarea id="proposito" placeholder="Escribe tu propósito..."></textarea>
<button onclick="enviarProposito()">Enviar</button>
<p id="mensaje" style="text-align:center;font-weight:bold;color:#c2185b;"></p>
</section>

<script>
let editNutri=null, editAdo=null;

// ===== NUTRICIONISTAS =====
function guardarNutri(){
  if(editNutri){
    editNutri.children[0].innerText=nid.value;
    editNutri.children[1].innerText=nnombre.value;
    editNutri.children[2].innerText=nedad.value;
    editNutri=null;
  }else{
    tablaNutri.innerHTML+=`
    <tr>
      <td>${nid.value}</td>
      <td>${nnombre.value}</td>
      <td>${nedad.value}</td>
      <td>
        <button onclick="editarNutri(this)">Editar</button>
        <button onclick="this.parentElement.parentElement.remove()">Eliminar</button>
      </td>
    </tr>`;
  }
  nid.value=nnombre.value=nedad.value="";
}

function editarNutri(btn){
  editNutri=btn.parentElement.parentElement;
  nid.value=editNutri.children[0].innerText;
  nnombre.value=editNutri.children[1].innerText;
  nedad.value=editNutri.children[2].innerText;
}

// ===== ADOLESCENTES =====
function guardarAdo(){
  let imc=(peso.value/(altura.value**2)).toFixed(2);
  let estado=imc<18.5?"Bajo peso":imc<25?"Normal":imc<30?"Sobrepeso":"Obesidad";

  if(editAdo){
    editAdo.children[0].innerText=anombre.value;
    editAdo.children[1].innerText=aedad.value;
    editAdo.children[2].innerText=altura.value;
    editAdo.children[3].innerText=peso.value;
    editAdo.children[4].innerText=imc;
    editAdo.children[5].innerText=estado;
    editAdo=null;
  }else{
    tablaAdo.innerHTML+=`
    <tr>
      <td>${anombre.value}</td>
      <td>${aedad.value}</td>
      <td>${altura.value}</td>
      <td>${peso.value}</td>
      <td>${imc}</td>
      <td>${estado}</td>
      <td>
        <button onclick="editarAdo(this)">Editar</button>
        <button onclick="this.parentElement.parentElement.remove()">Eliminar</button>
      </td>
    </tr>`;
  }
  anombre.value=aedad.value=altura.value=peso.value="";
}

function editarAdo(btn){
  editAdo=btn.parentElement.parentElement;
  anombre.value=editAdo.children[0].innerText;
  aedad.value=editAdo.children[1].innerText;
  altura.value=editAdo.children[2].innerText;
  peso.value=editAdo.children[3].innerText;
}

// ===== PROPÓSITOS =====
let frases=[
  "🌸 Cree en ti, lo estás haciendo bien",
  "💪 Cada esfuerzo suma",
  "🔥 La constancia vence al talento",
  "✨ Tu salud es tu prioridad",
  "🏆 Paso a paso se logran las metas"
];

function enviarProposito(){
  mensaje.innerText=frases[Math.floor(Math.random()*frases.length)];
  proposito.value="";
}
</script>

</body>
</html>
