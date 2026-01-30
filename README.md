<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>💗 Forgive Me 💗</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
body {
  margin: 0;
  height: 100vh;
  background: linear-gradient(180deg, #ffd1dc, #ffb3c6);
  display: flex;
  justify-content: center;
  align-items: center;
  font-family: "Poppins", sans-serif;
  overflow: hidden; 
}

.card {
  background: #fff7fa;
  padding: 40px 25px;
  border-radius: 30px;
  width: 90%;
  max-width: 420px;
  text-align: center;
  box-shadow: 0 18px 40px rgba(0,0,0,0.18);
  animation: fadeIn 1s ease;
}

@keyframes fadeIn {
  from { opacity: 0; transform: translateY(25px); }
  to { opacity: 1; transform: translateY(0); }
}

h1 {
  color: #ff4d88;
  font-size: 26px;
}

p {
  font-size: 17px;
  color: #555;
  line-height: 1.7;
  min-height: 160px;
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
}

button {
  padding: 12px 26px;
  border-radius: 25px;
  border: none;
  cursor: pointer;
  font-size: 16px;
  margin: 10px;
}

#heartBtn {
  font-size: 44px;
  background: none;
  animation: pulse 1.5s infinite;
}

@keyframes pulse {
  0% { transform: scale(1); }
  50% { transform: scale(1.15); }
  100% { transform: scale(1); }
}

.yes {
  background: #ff4d88;
  color: white;
}

.no {
  background: #e0e0e0;
  color: #555;
}

.hidden { display: none; }

/* floating hearts */
.heart {
  position: absolute;
  font-size: 24px;
  animation: float 7s linear infinite;
}

@keyframes float {
  from { transform: translateY(100vh); opacity: 1; }
  to { transform: translateY(-10vh); opacity: 0; }
}

/* confetti */
.confetti {
  position: fixed;
  top: 0;
  width: 10px;
  height: 10px;
  background: pink;
  animation: fall 3s linear infinite;
}

@keyframes fall {
  to { transform: translateY(100vh) rotate(360deg); }
}
</style>
</head>

<body>

<div class="heart" style="left:15%">💗</div>
<div class="heart" style="left:45%; animation-delay:2s;">💖</div>
<div class="heart" style="left:75%; animation-delay:4s;">💕</div>

<div class="card">
  <h1>💖 Mwiya Beyonce Mwiza 💖</h1>

  <p id="text"></p>

  <button id="heartBtn">💗</button>

  <div id="choices" class="hidden">
    <p>Will you forgive me? 🥺💞</p>
    <button class="yes" onclick="forgiven()">Yes 💕</button>
    <button class="no" onclick="notYet()">Not yet</button>
  </div>

  <!-- AUTO-PLAY MUSIC (muted first) -->
  <iframe id="music"
    width="0"
    height="0"
    src="https://www.youtube.com/embed/WcIcVapfqXw?autoplay=1&mute=1&loop=1&playlist=WcIcVapfqXw"
    allow="autoplay">
  </iframe>
</div>

<script>
const textEl = document.getElementById("text");
const heartBtn = document.getElementById("heartBtn");
const choices = document.getElementById("choices");
const music = document.getElementById("music");

const message = `
My love ❤️

I am truly sorry for saying bad words to you.
I promise from my heart that I will never say bad words again.

Please forgive me, Mwiya Beyonce Mwiza 🌸

— Lifasi Malumo Lucky
`;

let index = 0;
let unmuted = false;

// typing starts immediately
window.onload = () => typeText();

// unmute music on first tap anywhere
document.body.addEventListener("click", () => {
  if (!unmuted) {
    music.src = music.src.replace("&mute=1", "");
    unmuted = true;
  }
});

function typeText() {
  if (index < message.length) {
    textEl.innerHTML += message.charAt(index);
    index++;
    setTimeout(typeText, 40);
  } else {
    choices.classList.remove("hidden");
  }
}

heartBtn.onclick = () => {
  heartBtn.style.display = "none";
};

function forgiven() {
  textEl.innerHTML = `
Thank you for forgiving me 💗<br><br>
You mean everything to me.<br>
I promise to love you with respect,
calmness, and honesty always 🌷<br><br>

— Lifasi Malumo Lucky
`;
  choices.style.display = "none";
  celebrate();
}

function notYet() {
  textEl.innerHTML = `
I understand 💔<br><br>
Take your time…  
I’ll be right here, still choosing you 💗<br><br>

— Lifasi Malumo Lucky
`;
}

function celebrate() {
  for (let i = 0; i < 60; i++) {
    const confetti = document.createElement("div");
    confetti.className = "confetti";
    confetti.style.left = Math.random() * 100 + "vw";
    confetti.style.background =
      ["#ff4d88","#ffb3c6","#ffd1dc"][Math.floor(Math.random()*3)];
    confetti.style.animationDuration =
      (2 + Math.random() * 2) + "s";
    document.body.appendChild(confetti);
    setTimeout(() => confetti.remove(), 4000);
  }
}
</script>

</body>
</html>
