<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>para yasmin {meu amor}</title>
  <style>
    body {
      background: #000;
      margin: 0;
      padding: 0;
      font-family: 'Segoe UI', sans-serif;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      overflow: hidden;
      color: white;
    }

    .envelope {
      position: relative;
      width: 320px;
      height: 220px;
      background: #8B4513;
      border-radius: 8px;
      box-shadow: 0 0 20px rgba(255, 0, 0, 0.5);
      cursor: pointer;
      transition: transform 1s ease-in-out;
      transform-style: preserve-3d;
    }

    .envelope.open {
      transform: rotateX(180deg);
    }

    .heart {
      position: absolute;
      top: -25px;
      left: 50%;
      transform: translateX(-50%);
      font-size: 2em;
      color: red;
    }

    .scissors {
      position: absolute;
      top: 5px;
      right: 5px;
      font-size: 1.5em;
      cursor: pointer;
      z-index: 10;
      user-select: none;
    }

    .letter {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: #fffbe6;
      color: #5a2d0c;
      border-radius: 8px;
      padding: 20px;
      box-sizing: border-box;
      opacity: 0;
      transform: rotateX(180deg);
      backface-visibility: hidden;
      transition: opacity 0.6s ease-in;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      text-align: center;
    }

    .envelope.open .letter {
      opacity: 1;
    }

    .letter h2 {
      margin-bottom: 10px;
    }

    .contador {
      margin-top: 10px;
      font-size: 0.95em;
      color: #a0522d;
    }

    /* Responsividade para celular */
    @media (max-width: 400px) {
      .envelope {
        width: 90vw;
        height: auto;
        min-height: 180px;
      }
      .letter {
        padding: 15px;
      }
      .heart {
        font-size: 1.5em;
        top: -20px;
      }
      .scissors {
        font-size: 1.2em;
        top: 3px;
        right: 3px;
      }
      .letter p {
        font-size: 1em;
      }
      .contador {
        font-size: 0.85em;
      }
    }
  </style>
</head>
<body>
  <div class="envelope" id="carta">
    <div class="heart">❤️</div>
    <div class="scissors" onclick="abrirCarta()">✂️</div>
    <div class="letter">
      <h2>Meu Amor Infinito</h2>
      <p>
        Eu te amo demais meu amor e quero passar minha vida inteira com vc minha prinscesa. ❤️
      </p>
      <div class="contador" id="contador"></div>
    </div>
  </div>

  <script>
    function abrirCarta() {
      document.getElementById("carta").classList.toggle("open");
    }

    function atualizarContador() {
      const inicio = new Date("2024-11-11T00:00:00");
      const agora = new Date();
      const diff = agora - inicio;

      const dias = Math.floor(diff / (1000 * 60 * 60 * 24));
      const horas = Math.floor((diff / (1000 * 60 * 60)) % 24);
      const minutos = Math.floor((diff / (1000 * 60)) % 60);
      const segundos = Math.floor((diff / 1000) % 60);

      const texto = `Te amo desde 11/11/2024 — há ${dias} dias, ${horas} horas, ${minutos} minutos e ${segundos} segundos 💖`;

      document.getElementById("contador").textContent = texto;
    }

    setInterval(atualizarContador, 1000);
    atualizarContador();
  </script>
</body>
</html>
