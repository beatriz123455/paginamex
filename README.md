<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Mexicanismos</title>
  <style>
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background-color: #add8e6;
      overflow: hidden;
    }

    .section {
      display: none;
      padding: 20px;
      text-align: center;
    }

    .active {
      display: block;
    }

    .decoracion-superior {
      width: 100%;
      height: 10px;
      background: linear-gradient(to right, red 50%, green 50%);
    }

    .logo {
      width: 600px;
      margin: 20px auto;
    }

    button {
      margin: 10px;
      padding: 10px 20px;
      font-size: 16px;
      border: none;
      border-radius: 8px;
      background-color: #007BFF;
      color: white;
      cursor: pointer;
    }

    button:hover {
      background-color: #0056b3;
    }

    .burbuja {
      position: absolute;
      border-radius: 50%;
      opacity: 0.6;
      animation: flotar 20s linear infinite;
    }

    @keyframes flotar {
      0% { transform: translateY(100vh) scale(1); }
      100% { transform: translateY(-100vh) scale(1.5); }
    }

    .mapa {
      width: 300px;
      margin: auto;
      position: relative;
    }

    .estado-mexico {
      color: red;
      font-weight: bold;
    }

    .popup {
      display: none;
      position: absolute;
      background: white;
      border: 1px solid #ccc;
      padding: 10px;
      font-size: 14px;
      border-radius: 6px;
    }

    .habilidades button {
      display: inline-block;
      width: 120px;
    }

    .ejercicio {
      margin-top: 20px;
    }

    .ejercicio select {
      padding: 5px;
    }

  </style>
</head>
<body>

<div class="decoracion-superior"></div>

<!-- Página 1 - Bienvenida -->
<div class="section active" id="bienvenida">
  <h1>¡Bienvenido a los Mexicanismos!</h1>
  <img class="logo" src="quetzall-removebg.jpg" style="mix-blend-mode: multiply;">
 
  <button onclick="mostrar('presentacion')">Comenzar</button>
</div>

<!-- Página 2 - Presentación -->
<div class="section" id="presentacion">
  <h2>¿Qué es un Quetzal?</h2>
  <img src="quetzal-removebg.jpg" width="200" style="mix-blend-mode: multiply;">
  <p>El quetzal es un ave sagrada y símbolo de libertad en Mesoamérica. ¡Al igual que los mexicanismos que conocerás!</p>
  <p>Los mexicanismos son expresiones únicas que reflejan la cultura y forma de hablar de México.</p>
  <button onclick="mostrar('edad')">Siguiente</button>
</div>

<!-- Página 3 - Edad -->
<div class="section" id="edad">
  <h2>Selecciona tu edad</h2>
  <button disabled>Mayor de 18 años</button>
  <button onclick="mostrar('motivo')">Menor de 18 años</button>
</div>

<!-- Página 4 - Motivo -->
<div class="section" id="motivo">
  <h2>¿Para qué quieres aprender mexicanismos?</h2>
  <button disabled>Turismo</button>
  <button disabled>Relación social</button>
  <button onclick="mostrar('mapa')">Escolar</button>
</div>

<!-- Página 5 - Mapa -->
<div class="section" id="mapa">
  <h2>Explora los estados de México</h2>
  <div class="mapa" onmouseover="mostrarPopup()" onmouseout="ocultarPopup()">
    <img src="06-mexico_mapa_de_los_estados_s.jpg" width="300" alt="Mapa México">
    <div class="popup" id="popup" style="top: 20px; left: 100px;">
      <strong>Estado de México</strong><br>
      Lugares históricos: Teotihuacán, Toluca, Valle de Bravo.<br>
      Mexicanismo: "¡Qué chido!" = Qué bueno, qué padre.
      <br><img src="mapa-removebg-preview.jpg" width="150">
      <br><button onclick="mostrar('habilidades')">Comenzar</button>
    </div>
  </div>
</div>

<!-- Página 6 - Habilidades -->
<div class="section" id="habilidades">
  <h2>Elige una habilidad</h2>
  <div class="habilidades">
    <button onclick="mostrar('lee')">Lee</button>
    <button onclick="alert('Esta opción aún no está disponible')">Escucha</button>
    <button onclick="alert('Esta opción aún no está disponible')">Habla</button>
  </div>
  
</div>

<!-- Página 7 - Leer -->
<div class="section" id="lee">
  <h2>Mexicanismos vs Inglés</h2>
  <p>"¡Qué chido!" → "That's cool!"</p>
  <p>"No manches" → "No way!"</p>
  <p>"Órale" → "Wow!" o "Let's go!"</p>

  <div class="ejercicio">
    <h3>¿Cuál es el equivalente de "¡Qué padre!"?</h3>
    <select>
      <option>That’s boring</option>
      <option>That’s awesome</option>
      <option>That’s ugly</option>
    </select>
  </div>

  <br><button onclick="mostrar('habilidades')">Volver</button>
</div>

<!-- Burbujas de colores -->
<script>
  function crearBurbujas() {
    for (let i = 0; i < 20; i++) {
      let burbuja = document.createElement('div');
      burbuja.classList.add('burbuja');
      burbuja.style.width = burbuja.style.height = Math.random() * 40 + 20 + 'px';
      burbuja.style.left = Math.random() * window.innerWidth + 'px';
      burbuja.style.backgroundColor = `hsl(${Math.random() * 360}, 100%, 70%)`;
      burbuja.style.animationDuration = Math.random() * 20 + 10 + 's';
      document.body.appendChild(burbuja);
    }
  }

  function mostrar(id) {
    document.querySelectorAll('.section').forEach(s => s.classList.remove('active'));
    document.getElementById(id).classList.add('active');
  }

  function mostrarPopup() {
    document.getElementById('popup').style.display = 'block';
  }

  function ocultarPopup() {
    document.getElementById('popup').style.display = 'none';
  }

  crearBurbujas();
</script>

</body>
</html>
