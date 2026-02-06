# Navya-<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Navya ❤️</title>

  <style>
    * {
      box-sizing: border-box;
      font-family: "Poppins", "Comic Sans MS", sans-serif;
    }

    body {
      margin: 0;
      height: 100vh;
      background: linear-gradient(135deg, #ff758c, #ff7eb3);
      display: flex;
      align-items: center;
      justify-content: center;
      text-align: center;
      overflow: hidden;
    }

    .card {
      background: white;
      padding: 30px 20px;
      border-radius: 22px;
      box-shadow: 0 20px 40px rgba(0,0,0,0.25);
      max-width: 90%;
      width: 360px;
      position: relative;
      z-index: 2;
    }

    h1 {
      color: #ff4d6d;
      font-size: 26px;
      margin-bottom: 10px;
    }

    p {
      color: #555;
      font-size: 16px;
      margin-bottom: 25px;
    }

    .buttons {
      position: relative;
      height: 120px;
    }

    button {
      border: none;
      padding: 12px 26px;
      font-size: 18px;
      border-radius: 30px;
      cursor: pointer;
      transition: 0.2s;
    }

    #yes {
      background: #ff4d6d;
      color: white;
      box-shadow: 0 8px 18px rgba(255,77,109,0.5);
    }

    #yes:hover {
      transform: scale(1.1);
    }

    #no {
      position: absolute;
      background: #eee;
      color: #333;
      left: 55%;
      top: 60%;
    }

    /* Floating hearts */
    .heart {
      position: absolute;
      bottom: -20px;
      font-size: 20px;
      animation: floatUp 6s linear infinite;
      opacity: 0.8;
    }

    @keyframes floatUp {
      0% {
        transform: translateY(0) scale(1);
        opacity: 0;
      }
      20% {
        opacity: 1;
      }
      100% {
        transform: translateY(-120vh) scale(1.5);
        opacity: 0;
      }
    }

    /* Celebration screen */
    .celebrate {
      position: fixed;
      inset: 0;
      background: radial-gradient(circle, #ff9a9e, #ff4d6d);
      display: none;
      align-items: center;
      justify-content: center;
      flex-direction: column;
      z-index: 5;
      color: white;
      text-align: center;
      animation: popIn 0.8s ease;
    }

    @keyframes popIn {
      from { transform: scale(0.8); opacity: 0; }
      to { transform: scale(1); opacity: 1; }
    }

    .celebrate h1 {
      font-size: 36px;
      margin-bottom: 10px;
    }

    .celebrate p {
      font-size: 20px;
    }

    .confetti {
      position: absolute;
      width: 10px;
      height: 10px;
      background: white;
      animation: fall 3s linear infinite;
    }

    @keyframes fall {
      0% {
        transform: translateY(-10vh) rotate(0deg);
        opacity: 1;
      }
      100% {
        transform: translateY(110vh) rotate(360deg);
        opacity: 0;
      }
    }
  </style>
</head>

<body>

  <!-- Floating hearts container -->
  <div id="hearts"></div>

  <div class="card">
    <h1>Hey Navya ❤️</h1>
    <p>I’ve been wanting to ask you something really special 🥹</p>
    <h1>Will you be mine?</h1>

    <div class="buttons">
      <button id="yes">YES 💖</button>
      <button id="no">NO 🙈</button>
    </div>
  </div>

  <!-- Celebration screen -->
  <div class="celebrate" id="celebrate">
    <h1>YAYYYY 💕🎉</h1>
    <p>Navya, you just made my heart skip a beat 🥰<br>
       This is the happiest YES ever 💖</p>
  </div>

  <script>
    const noBtn = document.getElementById("no");
    const yesBtn = document.getElementById("yes");
    const celebrate = document.getElementById("celebrate");
    const heartsContainer = document.getElementById("hearts");

    function moveNoButton() {
      const x = Math.random() * 200 - 100;
      const y = Math.random() * 200 - 100;
      noBtn.style.transform = `translate(${x}px, ${y}px)`;
    }

    noBtn.addEventListener("mouseover", moveNoButton);
    noBtn.addEventListener("touchstart", moveNoButton);

    yesBtn.addEventListener("click", () => {
      celebrate.style.display = "flex";
      createConfetti();
    });

    // Floating hearts
    function createHeart() {
      const heart = document.createElement("div");
      heart.classList.add("heart");
      heart.innerHTML = "❤️";
      heart.style.left = Math.random() * 100 + "vw";
      heart.style.animationDuration = 4 + Math.random() * 3 + "s";
      heartsContainer.appendChild(heart);

      setTimeout(() => {
        heart.remove();
      }, 7000);
    }

    setInterval(createHeart, 500);

    // Confetti celebration
    function createConfetti() {
      for (let i = 0; i < 80; i++) {
        const confetti = document.createElement("div");
        confetti.classList.add("confetti");
        confetti.style.left = Math.random() * 100 + "vw";
        confetti.style.background = `hsl(${Math.random() * 360}, 100%, 70%)`;
        confetti.style.animationDuration = 2 + Math.random() * 2 + "s";
        document.body.appendChild(confetti);

        setTimeout(() => {
          confetti.remove();
        }, 4000);
      }
    }
  </script>

</body>
</html>
