<!DOCTYPE html>
<html lang="es">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>YourBirthdayCountdown</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: 'Playfair Display', serif;
      background-color: #f5f0f6;
      color: #5a3a6f;
      text-align: center;
    }

    .container {
      width: 100%;
      max-width: 800px;
      margin: 0 auto;
      padding: 20px;
    }

    .header h1 {
      font-size: 3rem;
      color: #9b2d91;
      margin-bottom: 20px;
    }

    .highlight {
      font-size: 2rem;
      font-weight: bold;
      color: #5a3a6f;
    }

    p {
      margin-bottom: 20px;
    }

    .countdown {
      margin-top: 30px;
    }

    .countdown h2 {
      font-size: 2rem;
      color: #9b2d91;
      margin-bottom: 20px;
    }

    .countdown-timer {
      margin-top: 20px;
      color: #9b2d91;
      font-weight: bold;
      font-size: 2rem;
    }

    .countdown-timer span {
      font-size: 2rem;
      animation: blink 1s infinite;
    }

    @keyframes blink {
      0% {
        opacity: 1;
      }

      50% {
        opacity: 0.5;
      }

      100% {
        opacity: 1;
      }
    }

    .map,
    .roadtrip {
      margin-top: 30px;
    }

    .roadtrip img,
    .map img {
      width: 100%;
      max-width: 600px;
      border-radius: 10px;
    }

    .lockbox {
      margin-top: 30px;
      background-color: #e0c9d0;
      padding: 20px;
      border-radius: 8px;
      display: inline-block;
    }

    .lock-icon {
      font-size: 2rem;
      color: #9b2d91;
    }

    .lock-icon span {
      font-size: 3rem;
    }

    #countdown-time {
      font-weight: bold;
      font-size: 2rem;
    }

    /* Estilo para el reloj digital animado */
    .digital-clock {
      font-family: 'Courier New', Courier, monospace;
      font-size: 3rem;
      color: #9b2d91;
      margin: 30px auto;
      padding: 20px;
      background-color: #f5f0f6;
      border-radius: 10px;
      display: inline-block;
      box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
      width: 50%;
    }

    .digital-clock span {
      display: inline-block;
      width: 50px;
      text-align: center;
    }

    .digital-clock span:nth-child(2),
    .digital-clock span:nth-child(5),
    .digital-clock span:nth-child(8) {
      padding: 0 10px;
    }
  </style>
</head>

<body>
  <div class="container">
    <div class="header">
      <h1>¡Feliz cumpleaños, mi amor! 🎉🎂</h1>
      <p>Hoy celebramos tu 26° cumpleaños y quiero aprovechar esta ocasión tan especial para recordarte lo increíble que eres. Este año, apenas hemos comenzado nuestra meta de viajar cada mes a un lugar nuevo, pero estoy emocionada de seguir cumpliéndola contigo y de crear recuerdos juntas.</p>
      <p>Como parte de nuestro compromiso y para celebrar todo lo que hemos logrado hasta ahora, quiero regalarte algo muy especial: un mini viaje para que pasemos juntas momentos inolvidables. 🗺️❤️‍🩹</p>
      <p>Estoy segura de que será una experiencia increíble, como todas las que compartimos. Te amo y espero que este día esté lleno de sonrisas, amor y mucha felicidad. 🎈❤️‍🩹</p>
      <p>Con todo mi amor, Clara 💫.</p>
    </div>

    <div class="roadtrip">
      <h3>¡AMOR MÍO! El día tan esperado está por llegar…</h3>
      <img src="https://digitaltravelcouple.com/wp-content/uploads/2023/08/Milford-Sound-roadtrip.jpg-2.webp"
        alt="Roadtrip aventura">
    </div>

    <div class="countdown">
      <p>Cuando el reloj marque cero, <span class="highlight">¡NOS VAMOS A BARICHARA!</span></p>

      <!-- Aquí se coloca el reloj digital animado -->
      <div class="digital-clock" id="digital-clock">
        <span id="days">00</span>:<span id="hours">00</span>:<span id="minutes">00</span>:<span id="seconds">00</span>
      </div>

      <h2>Este viaje será solo el comienzo de nuevas aventuras, y quiero que lo esperemos con todo el amor y la emoción del mundo.</h2>
    </div>

    <div class="place">
      <h3>TE AMO ❤️‍🩹, y no puedo esperar más para vivir este momento contigo.</h3>

      <!-- Aquí aparece el temporizador en formato numérico -->
      <div class="countdown-timer">
        <span id="timer"></span>
      </div>

      <p>Cuando el reloj llegue a cero, podremos incluir fotos y videos del viaje para guardar y plasmar en la página web. ❤️‍🩹</p>

      <div class="lockbox">
        <p><strong>Faltan <span id="countdown-time">00 días, 00 horas, 00 minutos, 00 segundos</span> para desbloquear...</strong></p>
        <div class="lock-icon">
          <span>🔒</span>
        </div>
      </div>
    </div>
  </div>

  <script>
    // Configurar la fecha para el viaje (28 de febrero de 2025)
    const targetDate = new Date("February 28, 2025 00:00:00").getTime();

    // Función para actualizar el temporizador digital
    function updateCountdown() {
      const now = new Date().getTime();
      const timeRemaining = targetDate - now;

      const days = Math.floor(timeRemaining / (1000 * 60 * 60 * 24));
      const hours = Math.floor((timeRemaining % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
      const minutes = Math.floor((timeRemaining % (1000 * 60 * 60)) / (1000 * 60));
      const seconds = Math.floor((timeRemaining % (1000 * 60)) / 1000);

      // Actualizar el temporizador digital
      document.getElementById("days").innerHTML = days < 10 ? "0" + days : days;
      document.getElementById("hours").innerHTML = hours < 10 ? "0" + hours : hours;
      document.getElementById("minutes").innerHTML = minutes < 10 ? "0" + minutes : minutes;
      document.getElementById("seconds").innerHTML = seconds < 10 ? "0" + seconds : seconds;

      // Actualizar el temporizador numérico
      document.getElementById("countdown-time").innerHTML = days + " días, " + hours + " horas, " + minutes +
        " minutos, " + seconds + " segundos";
    }

    // Actualizar el temporizador cada 1 segundo
    setInterval(updateCountdown, 1000);
  </script>
</body>

</html>

