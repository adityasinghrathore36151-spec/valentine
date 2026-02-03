<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Arshiya, Be My Valentine 💖</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />

  <style>
    body {
      margin: 0;
      height: 100vh;
      font-family: 'Poppins', sans-serif;
      background: linear-gradient(135deg, #ff9a9e, #fad0c4);
      display: flex;
      align-items: center;
      justify-content: center;
      overflow: hidden;
    }

    .card {
      background: white;
      padding: 45px;
      border-radius: 30px;
      text-align: center;
      box-shadow: 0 25px 50px rgba(0,0,0,0.25);
      animation: pop 0.9s ease;
      position: relative;
      z-index: 2;
    }

    @keyframes pop {
      from { transform: scale(0.7); opacity: 0; }
      to { transform: scale(1); opacity: 1; }
    }

    h1 {
      color: #ff2e63;
      font-size: 38px;
      margin-bottom: 10px;
      animation: glow 2s infinite alternate;
    }

    @keyframes glow {
      from { text-shadow: 0 0 10px #ffb3c6; }
      to { text-shadow: 0 0 20px #ff2e63; }
    }

    p {
      font-size: 18px;
      color: #555;
    }

    .buttons {
      margin-top: 35px;
      position: relative;
      height: 120px;
    }

    button {
      padding: 16px 34px;
      font-size: 18px;
      border: none;
      border-radius: 40px;
      cursor: pointer;
      transition: 0.3s;
      position: absolute;
    }

    #yes {
      background: #ff2e63;
      color: white;
      left: 50%;
      transform: translateX(-120%);
    }

    #no {
      background: #e0e0e0;
      color: #333;
      left: 50%;
      transform: translateX(20%);
    }

    #yes:hover {
      background: #ff0844;
      transform: translateX(-120%) scale(1.1);
    }

    .result {
      display: none;
      text-align: center;
      animation: pop 0.8s ease;
    }

    .result img {
      width: 260px;
      margin-top: 25px;
      border-radius: 25px;
    }

    .confetti, .sparkle {
      position: fixed;
      pointer-events: none;
      z-index: 1;
    }

    .confetti {
      width: 10px;
      height: 10px;
      background: pink;
      animation: fall 4s linear infinite;
    }

    @keyframes fall {
      0% { transform: translateY(-100px) rotate(0); opacity: 1; }
      100% { transform: translateY(100vh) rotate(360deg); opacity: 0; }
    }

    .sparkle {
      font-size: 20px;
      animation: sparkle 2s infinite;
    }

    @keyframes sparkle {
      0% { opacity: 0; transform: scale(0); }
      50% { opacity: 1; transform: scale(1.3); }
      100% { opacity: 0; transform: scale(0); }
    }
  </style>
</head>

<body>

  <!-- Romantic background music -->
  <audio autoplay loop>
    <source src="https://cdn.pixabay.com/audio/2023/03/02/audio_5d75c7d4c2.mp3" type="audio/mpeg">
  </audio>

  <div class="card" id="question">
    <h1>ARSHIYA 💖</h1>
    <p>Will you be my Valentine?</p>
    <p style="font-size:14px;color:#888;">(Taylor Swift coded, I promise 💕)</p>

    <div class="buttons">
      <button id="yes">Yes 💕</button>
      <button id="no">No 😈</button>
    </div>
  </div>

  <div class="card result" id="result">
    <h1>IT’S A YESSS 💖✨</h1>
    <p>You just made my heart do cartwheels 🥹</p>
    <img src="https://media.giphy.com/media/MDJ9IbxxvDUQM/giphy.gif" alt="Happy Dog">
  </div>

  <script>
    const noBtn = document.getElementById("no");
    const yesBtn = document.getElementById("yes");
    const question = document.getElementById("question");
    const result = document.getElementById("result");

    noBtn.addEventListener("mouseover", () => {
      const x = Math.random() * 300 - 150;
      const y = Math.random() * 200 - 100;
      noBtn.style.transform = `translate(${x}px, ${y}px)`;
    });

    yesBtn.addEventListener("click", () => {
      question.style.display = "none";
      result.style.display = "block";
      launchConfetti();
      launchSparkles();
    });

    function launchConfetti() {
      for (let i = 0; i < 60; i++) {
        const confetti = document.createElement("div");
        confetti.className = "confetti";
        confetti.style.left = Math.random() * 100 + "vw";
        confetti.style.background = ["#ff2e63","#ffc2d1","#ffd6e0"][Math.floor(Math.random()*3)];
        confetti.style.animationDuration = Math.random() * 2 + 3 + "s";
        document.body.appendChild(confetti);
        setTimeout(() => confetti.remove(), 4000);
      }
    }

    function launchSparkles() {
      for (let i = 0; i < 25; i++) {
        const sparkle = document.createElement("div");
        sparkle.className = "sparkle";
        sparkle.innerHTML = "✨";
        sparkle.style.left = Math.random() * 100 + "vw";
        sparkle.style.top = Math.random() * 100 + "vh";
        document.body.appendChild(sparkle);
        setTimeout(() => sparkle.remove(), 2000);
      }
    }
  </script>

</body>
</html>
