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
  background: linear-gradient(180deg, #ffc0cb, #ffb6c1);
  display: flex;
  justify-content: center;
  align-items: center;
  font-family: "Poppins", sans-serif;
  overflow: hidden;
}

.card {
  background: #fff5f8;
  padding: 35px 25px;
  border-radius: 30px;
  width: 90%;
  max-width: 420px;
  text-align: center;
  box-shadow: 0 20px 40px rgba(0,0,0,0.2);
  animation: fadeIn 1s ease;
}

@keyframes fadeIn {
  from { opacity: 0; transform: translateY(20px); }
  to { opacity: 1; transform: translateY(0); }
}

h1 {
  color: #ff4f9a;
  font-size: 26px;
}

p {
  font-size: 17px;
  color: #555;
  line-height: 1.6;
  min-height: 140px;
}

button {
  padding: 12px 22px;
  border-radius: 25px;
  border: none;
  cursor: pointer;
  font-size: 16px;
  margin: 10px;
}

#heartBtn {
  font-size: 42px;
  background: none;
  animation: pulse 1.5s infinite;
}

@keyframes pulse {
  0% { transform: scale(1); }
  50% { transform: scale(1.15); }
  100% { transform: scale(1); }
}

.yes {
  background: #ff69b4;
  color: white;
}

.no {
  background: #ddd;
}

.hidden { display: none; }

/* floating hearts */
.heart {
  position: absolute;
  font-size: 24px;
  animation: float 6s linear infinite;
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

<div class="heart" style="left:10%">💗</div>
<div class="heart" style="left:50%; animation-delay:2s;">💖</div>
<div class="heart" style="left:80%; animation-delay:4s;">💕</div>

<div class="card">
  <h1>💖 Mwiya Beyonce Mwiza 💖</h1>

  <p id="text"></p>

  <button id="heartBtn">💗</button>

  <div id="choices" class="hidden">
    <p>Will you forgive me? 🥺</p>
    <button class="yes" onclick="forgiven()">Yes 💕</button>
    <button class="no" onclick="notYet()">Not yet</button>
  </div>

  <div id="music" class="hidden">
    <iframe width="0" height="0"
      src="https://www.youtube.com/embed/WcIcVapfqXw?autoplay=1&loop=1&playlist=WcIcVapfqXw"
      allow="autoplay">
    </iframe>
  </div>
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

— Lifasi
`;

let index = 0;

heartBtn.onclick = () => {
  music.classList.remove("hidden");
  heartBtn.style.display = "none";
  typeText();
};

function typeText() {
  if (index < message.length) {
    textEl.innerHTML += message.charAt(index);
    index++;
    setTimeout(typeText, 40);
  } else {
    choices.classList.remove("hidden");
  }
}

function forgiven() {
  textEl.innerHTML = `
Thank you for forgiving me 💗<br><br>
You mean everything to me.<br>
I promise to love you with respect, calmness,
and honesty always 🌷
`;
  choices.style.display = "none";
  celebrate();
}

function notYet() {
  textEl.innerHTML = `
I understand 💔<br><br>
Take your time…  
I’ll be right here, still choosing you 💗
`;
}

function celebrate() {
  for (let i = 0; i < 60; i++) {
    const confetti = document.createElement("div");
    confetti.className = "confetti";
    confetti.style.left = Math.random() * 100 + "vw";
    confetti.style.background = ["#ff69b4","#ffc0cb","#ffb6c1"][Math.floor(Math.random()*3)];
    confetti.style.animationDuration = (2 + Math.random() * 2) + "s";
    document.body.appendChild(confetti);

    setTimeout(() => confetti.remove(), 4000);
  }
}
</script>

</body>
</html>
