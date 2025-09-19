<!DOCTYPE html>
<html lang="tr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Barışma Sayacı</title>
<style>
  body {
    font-family: Arial, sans-serif;
    text-align: center;
    padding: 50px;
    background: linear-gradient(to right, #fbc2eb, #a6c1ee);
    min-height: 100vh;
    margin: 0;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }

  h1 {
    font-size: 2em;
    color: #333;
    margin-bottom: 40px;
  }

  button {
    background-color: #4CAF50;
    border: none;
    color: white;
    padding: 15px 40px;
    margin: 10px;
    font-size: 18px;
    border-radius: 12px;
    cursor: pointer;
    transition: transform 0.3s, background-color 0.3s;
  }

  button:hover {
    background-color: #45a049;
  }

  #count, #thanks {
    font-size: 1.5em;
    margin-top: 30px;
    color: #333;
  }

  #thanks {
    font-size: 2em;
    color: #ff0000;
    margin-top: 20px;
    display: none;
  }

  @media (max-width: 600px) {
    h1 { font-size: 1.5em; }
    button { padding: 12px 30px; font-size: 16px; }
    #count, #thanks { font-size: 1.2em; }
  }
</style>
</head>
<body>
<h1>Benimle barışır mısın?</h1>
<button id="yesBtn">Evet</button>
<button id="noBtn">Hayır</button>
<div id="count">Hayır sayısı: 0</div>
<div id="thanks">Teşekkürler!</div>

<script>
let count = 0;
const yesBtn = document.getElementById("yesBtn");
const noBtn = document.getElementById("noBtn");
const countDiv = document.getElementById("count");
const thanksDiv = document.getElementById("thanks");

noBtn.onclick = function() {
    count++;
    countDiv.innerText = "Hayır sayısı: " + count;

    // Evet butonunu büyüt ve normal boyuta dönmesin
    yesBtn.style.transform = "scale(" + (1 + 0.1 * count) + ")";

    // 5 tıklamadan sonra Hayır butonunu gizle
    if (count >= 5) {
        noBtn.style.display = "none";
        countDiv.innerText = "Hayır sayısı: 5 (Artık sadece evet var!)";
    }
};

yesBtn.onclick = function() {
    // Konfeti patlat
    for(let i=0;i<100;i++){
        let confetti = document.createElement("div");
        confetti.style.position = "fixed";
        confetti.style.width = "10px";
        confetti.style.height = "10px";
        confetti.style.background = "hsl(" + Math.random()*360 + ", 100%, 50%)";
        confetti.style.top = Math.random()*window.innerHeight + "px";
        confetti.style.left = Math.random()*window.innerWidth + "px";
        confetti.style.borderRadius = "50%";
        confetti.style.zIndex = "9999";
        document.body.appendChild(confetti);
        setTimeout(()=>confetti.remove(),2000);
    }

    // Teşekkürler yazısını göster
    thanksDiv.style.display = "block";
};
</script>
</body>
</html>

