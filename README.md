# mylovee
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>My Love Rain</title>
  <style>
    html, body {
      margin: 0;
      padding: 0;
      overflow: hidden;
      background: #000;
      height: 100%;
      font-family: 'Share Tech Mono', monospace;
    }

    .rain-container {
      position: relative;
      width: 100vw;
      height: 100vh;
    }

    .drop {
      position: absolute;
      color: #ff69b4;
      font-size: 1rem;
      white-space: nowrap;
      animation: fall linear infinite;
      text-shadow:
        0 0 5px #ff69b4,
        0 0 10px #ff69b4,
        0 0 20px #ff69b4;
    }

    @keyframes fall {
      0% {
        transform: translateY(-100%);
        opacity: 0.6;
      }
      100% {
        transform: translateY(100vh);
        opacity: 0;
      }
    }
  </style>
</head>
<body>
  <div class="rain-container" id="rain"></div>

  <script>
    const container = document.getElementById('rain');
    const numberOfDrops = 300; // Ajusta este número según el rendimiento del navegador

    for (let i = 0; i < numberOfDrops; i++) {
      const drop = document.createElement('div');
      drop.classList.add('drop');
      drop.textContent = 'my love';

      // Posición horizontal aleatoria
      drop.style.left = Math.random() * 100 + 'vw';

      // Duración aleatoria
      const duration = 3 + Math.random() * 5;
      drop.style.animationDuration = duration + 's';

      // Retraso aleatorio
      drop.style.animationDelay = Math.random() * 5 + 's';

      // Tamaño aleatorio
      const fontSize = 14 + Math.random() * 20;
      drop.style.fontSize = fontSize + 'px';

      container.appendChild(drop);
    }
  </script>
</body>
</html>
