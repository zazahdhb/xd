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
    transition: background-color 0.3s, transform 0.2s;
  }

  button:hover {
    background-color: #45a049;
    transform: scale(1.1);
  }

  #count {
    font-size: 1.5em;
    margin-top: 30px;
    color: #333;
  }

  /* Mobil uyumlu boyutlar */
  @media (max-width: 600px) {
    h1 { font-size: 1.5em; }
    button { padding: 12px 30px; font-size: 16px; }
    #count { font-size: 1.2em; }
  }
</style>
</head>
<body>
<h1>Benimle barışır mısın?</h1>
<button id="yesBtn">Evet</button>
<button id="noBtn">Hayır</button>
<div id="count">Hayır sayısı: 0</div>

<script>
let count = 0;

document.getElementById("noBtn").onclick = function() {
    count++;
    document.getElementById("count").innerText = "Hayır sayısı: " + count;
};

document.getElementById("yesBtn").onclick = function() {
    alert("Yayyy! Barıştınız! (çok başarısız oldu ilk deneyim özür dilerim)🎉🎉🎉");
    for(let i=0; i<100; i++){
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
};
</script>
</body>
</html>

