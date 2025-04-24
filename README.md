# Wally-Eventos

<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Wally Eventos</title>
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;600&display=swap" rel="stylesheet">
  <style>
    body {
      margin: 0;
      font-family: 'Poppins', sans-serif;
      background-color: #fdfdfd;
      color: #333;
    }
    header {
      background: #3a269c;
      color: white;
      text-align: center;
      padding: 2rem 1rem;
      animation: fadeInDown 1s ease-out;
    }
    header h1 {
      margin: 0;
      font-size: 2.5rem;
    }
    header p {
      font-size: 1.2rem;
      margin-top: 0.5rem;
    }
    section {
      padding: 2rem;
      max-width: 1000px;
      margin: auto;
      animation: fadeInUp 1s ease-out;
    }
    .servicios {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
      gap: 1.5rem;
    }
    .servicio {
      border: 1px solid #ddd;
      border-radius: 12px;
      padding: 1rem;
      text-align: center;
      background: #fff;
      box-shadow: 0 2px 8px rgba(0,0,0,0.05);
      transition: transform 0.3s ease, box-shadow 0.3s ease;
    }
    .servicio:hover {
      transform: translateY(-5px);
      box-shadow: 0 4px 20px rgba(0,0,0,0.1);
    }
    .servicio h3 {
      margin-top: 0;
      color: #3a269c;
    }
    .ver-mas {
      margin-top: 0.8rem;
      display: inline-block;
      background: #3a269c;
      color: white;
      padding: 0.5rem 1rem;
      border-radius: 20px;
      font-size: 0.9rem;
      cursor: pointer;
      text-decoration: none;
    }
    .detalle-panel {
      display: none;
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100vh;
      background: rgba(0, 0, 0, 0.7);
      z-index: 1000;
      justify-content: center;
      align-items: center;
      padding: 2rem;
    }
    .detalle-contenido {
      background: white;
      border-radius: 12px;
      max-width: 600px;
      width: 100%;
      padding: 2rem;
      position: relative;
      animation: fadeInUp 0.5s ease-out;
    }
    .cerrar-panel {
      position: absolute;
      top: 1rem;
      right: 1rem;
      background: #3a269c;
      color: white;
      border: none;
      border-radius: 50%;
      width: 32px;
      height: 32px;
      font-size: 18px;
      cursor: pointer;
    }
    .whatsapp {
      position: fixed;
      bottom: 20px;
      right: 20px;
      background: #25d366;
      color: white;
      border-radius: 50%;
      width: 60px;
      height: 60px;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 30px;
      text-decoration: none;
      box-shadow: 0 4px 10px rgba(0,0,0,0.3);
      z-index: 999;
    }
    @keyframes fadeInDown {
      from { opacity: 0; transform: translateY(-20px); }
      to { opacity: 1; transform: translateY(0); }
    }
    @keyframes fadeInUp {
      from { opacity: 0; transform: translateY(20px); }
      to { opacity: 1; transform: translateY(0); }
    }
  </style>
</head>
<body>
  <header>
    <h1>Wally Eventos</h1>
    <p>Lo que quieras, nosotros lo hacemos realidad</p>
  </header>

  <section>
    <h2>Servicios</h2>
    <div class="servicios">
      <div class="servicio">
        <h3>Fiestas Sencillas</h3>
        <p>Celebraciones familiares y fiestas pequeñas con todo lo necesario.</p>
        <a class="ver-mas" onclick="abrirPanel('Fiestas Sencillas', 'Incluye decoración temática, sonido básico, coordinación y apoyo en logística. Nos encargamos de todo para que tú disfrutes.')">Ver más</a>
      </div>
      <div class="servicio">
        <h3>Matrimonios</h3>
        <p>Coordinación completa de tu boda soñada.</p>
        <a class="ver-mas" onclick="abrirPanel('Matrimonios', 'Ofrecemos planificación total, decoración elegante, ambientación, catering, música y todo lo necesario para que tu boda sea perfecta.')">Ver más</a>
      </div>
      <div class="servicio">
        <h3>Eventos Empresariales</h3>
        <p>Profesionalismo en eventos corporativos y lanzamientos.</p>
        <a class="ver-mas" onclick="abrirPanel('Eventos Empresariales', 'Manejo de agenda, sonido profesional, anfitriones, señalización, coffee break, y todos los detalles corporativos que marcan la diferencia.')">Ver más</a>
      </div>
      <div class="servicio">
        <h3>Servicios Adicionales</h3>
        <p>Complementos ideales para todo tipo de evento.</p>
        <a class="ver-mas" onclick="abrirPanel('Servicios Adicionales', 'Meseros, decoración especial, sonido, iluminación, registro de fotos y video profesional. Todo lo que necesites para que tu evento brille.')">Ver más</a>
      </div>
    </div>
  </section>

  <!-- Panel Dinámico -->
  <div id="panel" class="detalle-panel" onclick="cerrarPanel(event)">
    <div class="detalle-contenido" onclick="event.stopPropagation()">
      <button class="cerrar-panel" onclick="cerrarPanel(event)">✕</button>
      <h2 id="panel-titulo"></h2>
      <p id="panel-contenido"></p>
    </div>
  </div>

  <!-- Botón de WhatsApp -->
  <a class="whatsapp" href="https://wa.me/573124659313" target="_blank" title="Contáctanos por WhatsApp">
    💬
  </a>

  <script>
    function abrirPanel(titulo, contenido) {
      document.getElementById('panel-titulo').innerText = titulo;
      document.getElementById('panel-contenido').innerText = contenido;
      document.getElementById('panel').style.display = 'flex';
    }

    function cerrarPanel(event) {
      document.getElementById('panel').style.display = 'none';
    }
  </script>
</body>
</html>
