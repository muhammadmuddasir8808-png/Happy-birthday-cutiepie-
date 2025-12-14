<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Happy Birthday Anamta!</title>
<style>
body {
  margin: 0; padding: 0;
  display: flex; justify-content: center; align-items: center;
  height: 100vh; background: linear-gradient(to right, #ff9a9e, #fad0c4);
  font-family: 'Arial', sans-serif; overflow: hidden;
}
h1 { font-size: 3em; color: #fff; text-shadow: 2px 2px #000; animation: glow 1s infinite alternate; }
@keyframes glow {
  0% { text-shadow: 0 0 5px #fff; }
  100% { text-shadow: 0 0 20px #fff, 0 0 30px #ff0; }
}
#confetti { position: absolute; top: 0; left: 0; width: 100%; height: 100%; pointer-events: none; }
</style>
</head>
<body>
<h1>Happy Birthday Anamta 🎉</h1>
<canvas id="confetti"></canvas>
<script>
// Confetti animation
const canvas = document.getElementById('confetti');
const ctx = canvas.getContext('2d');
canvas.width = window.innerWidth;
canvas.height = window.innerHeight;
const pieces = [];
for(let i=0;i<150;i++){ pieces.push({x:Math.random()*canvas.width, y:Math.random()*canvas.height, r:Math.random()*6+2, d:Math.random()*1+1, color:`hsl(${Math.random()*360},100%,50%)`}); }
function draw(){ ctx.clearRect(0,0,canvas.width,canvas.height); pieces.forEach(p=>{ ctx.beginPath(); ctx.arc(p.x,p.y,p.r,0,Math.PI*2); ctx.fillStyle=p.color; ctx.fill(); p.y+=p.d; if(p.y>canvas.height){p.y=0; p.x=Math.random()*canvas.width;} }); requestAnimationFrame(draw); }
draw();
</script>
</body>
</html>
