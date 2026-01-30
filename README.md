<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Forgive Me 💖</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <style>
    body {
      margin: 0;
      height: 100vh;
      background: linear-gradient(135deg, #ffb6c1, #ffc0cb);
      display: flex;
      justify-content: center;
      align-items: center;
      font-family: "Comic Sans MS", cursive;
    }

    .card {
      background: #fff0f5;
      padding: 30px;
      border-radius: 25px;
      width: 90%;
      max-width: 420px;
      text-align: center;
      box-shadow: 0 15px 30px rgba(0,0,0,0.25);
    }

    h1 {
      color: #ff4f9a;
    }

    p {
      font-size: 18px;
      color: #555;
      margin: 20px 0;
    }

    button {
      font-size: 36px;
      background: none;
      border: none;
      cursor: pointer;
      transition: transform 0.2s;
    }

    button:hover {
      transform: scale(1.2);
    }

    .hidden {
      display: none;
    }

    iframe {
      margin-top: 15px;
      border-radius: 15px;
    }
  </style>
</head>
<body>

  <div class="card">
    <h1>💗 Mwiya Beyonce Mwiza 💗</h1>

    <p id="message">
      Tap the heart to hear the music and read my apology 💕
    </p>

    <button id="heartBtn">💖</button>

    <!-- Background music (hidden until click) -->
    <div id="music" class="hidden">
      <iframe
        width="0"
        height="0"
        src="https://www.youtube.com/embed/WcIcVapfqXw?autoplay=1&loop=1&playlist=WcIcVapfqXw"
        title="Rema Calm Down"
        allow="autoplay">
      </iframe>
    </div>
  </div>

  <script>
    const heartBtn = document.getElementById("heartBtn");
    const message = document.getElementById("message");
    const music = document.getElementById("music");

    let step = 0;

    heartBtn.addEventListener("click", () => {
      if (step === 0) {
        music.classList.remove("hidden");
        message.innerHTML = `
          My love ❤️<br><br>
          I am truly sorry for saying bad words to you.<br>
          I promise with all my heart that I will <b>never say bad words again</b>.<br><br>
          I am asking for your forgiveness,  
          <br><b>Mwiya Beyonce Mwiza 💕</b>
        `;
        heartBtn.textContent = "🥺💖";
        step = 1;
      } else {
        message.innerHTML = `
          Thank you for listening 💗<br><br>
          I hope this music reminds you how calm and real my love is for you 🌸
        `;
        heartBtn.textContent = "💞";
      }
    });
  </script>

</body>
</html>
