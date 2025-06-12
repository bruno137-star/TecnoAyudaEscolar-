# TecnoAyudaEscolar-<!DOCTYPE html><html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Diagnóstico Tecnológico</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #eef2f5;
      padding: 20px;
    }
    form {
      background: #fff;
      padding: 20px;
      border-radius: 10px;
      max-width: 600px;
      margin: auto;
      box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    }
    h2, h3 {
      color: #333;
    }
    label {
      display: block;
      margin-bottom: 8px;
    }
    button {
      margin-top: 20px;
      padding: 10px 20px;
      background-color: #3b82f6;
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }
    #resultado {
      margin-top: 30px;
      text-align: center;
      font-size: 1.2em;
      font-weight: bold;
    }
  </style>
</head>
<body>
  <form id="formularioDiagnostico">
    <h2>¿Qué tanto sabes de tecnología?</h2><h3>Sección 1: Uso general</h3>
<label><input type="checkbox" name="basico" value="1"> Enciendo un computador</label>
<label><input type="checkbox" name="basico" value="1"> Uso el mouse o pantalla táctil</label>
<label><input type="checkbox" name="basico" value="1"> Me conecto a internet</label>

<h3>Sección 2: Herramientas digitales</h3>
<label><input type="checkbox" name="intermedio" value="1"> Usé PowerPoint</label>
<label><input type="checkbox" name="intermedio" value="1"> Usé Canva</label>
<label><input type="checkbox" name="intermedio" value="1"> Envié trabajos digitales</label>

<h3>Sección 3: Actividades avanzadas</h3>
<label><input type="checkbox" name="experto" value="1"> Creo presentaciones solo/a</label>
<label><input type="checkbox" name="experto" value="1"> Trabajo en grupo con herramientas online</label>

<button type="submit">Ver mi nivel</button>

  </form>  <div id="resultado"></div>  <script>
    document.getElementById("formularioDiagnostico").addEventListener("submit", function (e) {
      e.preventDefault();

      const niveles = { basico: 0, intermedio: 0, experto: 0 };

      for (let nivel in niveles) {
        const checks = document.querySelectorAll(`input[name="${nivel}"]:checked`);
        niveles[nivel] = checks.length;
      }

      let resultado = "Nivel asignado: ";
      if (niveles.experto >= 2) {
        resultado += "🚀 EXPERTO";
      } else if (niveles.intermedio >= 2) {
        resultado += "🤩 INTERMEDIO";
      } else {
        resultado += "🔰 BÁSICO";
      }

      document.getElementById("resultado").innerText = resultado;
    });
  </script></body>
</html>
