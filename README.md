<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Happy Birthday Sayang ❤️</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      background: linear-gradient(135deg, #ff9a9e, #fad0c4);
      font-family: 'Poppins', sans-serif;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      height: 100vh;
      text-align: center;
      overflow: hidden;
    }
    h1 {
      font-size: 2.5rem;
      color: #fff;
      text-shadow: 2px 2px 5px rgba(0,0,0,0.2);
      opacity: 0;
      transform: translateY(-50px);
      transition: all 1s ease;
    }
    p {
      font-size: 1.2rem;
      color: #fff;
      opacity: 0;
      transition: all 1.5s ease;
    }
    button {
      margin-top: 20px;
      padding: 12px 25px;
      font-size: 1rem;
      border: none;
      border-radius: 25px;
      background: #ff6f61;
      color: #fff;
      cursor: pointer;
      transition: 0.3s;
    }
    button:hover {
      background: #ff3b2e;
    }
    .hidden {
      display: none;
    }
    .hearts {
      position: fixed;
      top: -10px;
      left: 50%;
      font-size: 2rem;
      color: red;
      animation: fall 5s linear infinite;
    }
    @keyframes fall {
      0% { transform: translateY(-10px) rotate(0deg); opacity: 1; }
      100% { transform: translateY(100vh) rotate(360deg); opacity: 0; }
    }
  </style>
</head>
<body>
  <h1 id="title">🎂 Happy Birthday Sayang 🎂</h1>
  <p id="message">Klik tombol di bawah ini untuk lihat surprise 💖</p>
  <button id="revealBtn">Buka Surprise 🎁</button>

  <div id="surprise" class="hidden">
    <h1>Selamat Ulang Tahun, Cintaku! ❤️</h1>
    <p>Semoga hari-harimu selalu indah, penuh cinta, kebahagiaan, dan doa terbaikku selalu untukmu 💕</p>
    <p>Love you forever 😘</p>
  </div>

  <audio id="song" src="https://www.computerhope.com/jargon/m/example.mp3"></audio>

  <script>
    const title = document.getElementById("title");
    const message = document.getElementById("message");
    const revealBtn = document.getElementById("revealBtn");
    const surprise = document.getElementById("surprise");
    const song = document.getElementById("song");

    // Animasi muncul awal
    window.onload = () => {
      setTimeout(() => title.style.opacity = 1, 500);
      setTimeout(() => message.style.opacity = 1, 1000);
    };

    // Klik tombol
    revealBtn.addEventListener("click", () => {
      surprise.classList.remove("hidden");
      revealBtn.style.display = "none";
      message.style.display = "none";
      song.play();

      // Efek hati jatuh
      setInterval(() => {
        const heart = document.createElement("div");
        heart.classList.add("hearts");
        heart.innerHTML = "❤️";
        heart.style.left = Math.random() * 100 + "vw";
        heart.style.fontSize = Math.random() * 20 + 15 + "px";
        document.body.appendChild(heart);
        setTimeout(() => heart.remove(), 5000);
      }, 500);
    });
  </script>
</body>
</html>
