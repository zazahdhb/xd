<!DOCTYPE html>
<html lang="tr">
<head>
<meta charset="UTF-8">
<title>Barışma Sayacı</title>
<style>
  body { font-family: Arial; text-align:center; padding:50px; background:#f0f0f0; }
  button { padding:10px 20px; margin:10px; font-size:16px; cursor:pointer; }
  #count { font-size:24px; margin-top:20px; }
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
    alert("Yayyy! Barıştınız! 🎉🎉🎉");
    for(let i=0;i<100;i++){
        let confetti = document.createElement("div");
        confetti.style.position = "fixed";
        confetti.style.width = "10px";
        confetti.style.height = "10px";
        confetti.style.background = "hsl(" + Math.random()*360 + ", 100%, 50%)";
        confetti.style.top = Math.random()*window.innerHeight + "px";
        confetti.style.left = Math.random()*window.innerWidth + "px";
        document.body.appendChild(confetti);
        setTimeout(()=>confetti.remove(),2000);
    }
};
</script>
</body>
</html>
