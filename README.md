<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Trần Tất Đạt - Trang cá nhân</title>
<style>
  :root {
    --bg-main: #e8f1f9;
    --bg-header1: #a6d9f7;
    --bg-header2: #7ec8f4;
    --bg-section: #edf5fb;
    --text-color: #333;
    --accent: #2196f3;
    --accent-strong: #1976d2;
    --footer-bg: #7ec8f4;
    --light-color: rgba(255,255,255,0.4);
  }

  body.dark {
    --bg-main: #0e1721;
    --bg-header1: #2b1b54;
    --bg-header2: #0b436b;
    --bg-section: rgba(20,25,35,0.7);
    --text-color: #e0e7ef;
    --accent: #64b5f6;
    --accent-strong: #90caf9;
    --footer-bg: #132030;
    --light-color: rgba(160,200,255,0.25);
  }

  body {
    font-family: "Segoe UI", sans-serif;
    margin: 0;
    background: var(--bg-main);
    color: var(--text-color);
    transition: background 0.6s ease, color 0.6s ease;
    overflow-x: hidden;
  }

  /* --- Canvas Aurora --- */
  #auroraCanvas {
    position: fixed;
    top: 0;
    left: 0;
    width: 100vw;
    height: 100vh;
    z-index: 0;
    pointer-events: none;
    opacity: 0;
    transition: opacity 1s ease;
  }
  body.dark #auroraCanvas { opacity: 1; }

  header {
    position: relative;
    text-align: center;
    background: linear-gradient(135deg, var(--bg-header1), var(--bg-header2));
    color: white;
    padding: 60px 20px;
    overflow: hidden;
    transition: background 2s ease;
    z-index: 2;
  }

  header h1 {
    font-size: 2.4em;
    margin: 0;
    cursor: pointer;
    user-select: none;
    transition: text-shadow 0.4s ease;
  }

  header p {
    font-size: 1.1em;
    margin-top: 10px;
  }

  .light-glow {
    position: absolute;
    top: 0;
    left: -50%;
    width: 50%;
    height: 100%;
    background: linear-gradient(
      120deg,
      rgba(255, 255, 255, 0) 0%,
      var(--light-color) 50%,
      rgba(255, 255, 255, 0) 100%
    );
    transform: skewX(-30deg);
    opacity: 0;
    pointer-events: none;
    transition: opacity 1s ease;
  }

  #modeToggle, #sennaButton {
    position: fixed;
    right: 25px;
    background: rgba(255,255,255,0.7);
    border: none;
    border-radius: 30px;
    padding: 10px 20px;
    cursor: pointer;
    font-weight: bold;
    color: #333;
    transition: all 0.4s ease;
    backdrop-filter: blur(4px);
    box-shadow: 0 2px 8px rgba(0,0,0,0.15);
    z-index: 2000;
  }

  #modeToggle { top: 20px; }
  #sennaButton { top: 70px; }

  body.dark #modeToggle,
  body.dark #sennaButton {
    background: rgba(0,0,0,0.4);
    color: #fff;
    box-shadow: 0 0 10px rgba(100,181,246,0.3);
  }

  main {
    position: relative;
    z-index: 3;
    max-width: 850px;
    background: var(--bg-section);
    margin: 40px auto;
    padding: 40px 50px;
    border-radius: 15px;
    box-shadow: 0 4px 10px rgba(0,0,0,0.1);
    transition: background 0.6s ease;
  }

  section {
    margin-bottom: 40px;
    background: var(--bg-section);
    border: 1px solid rgba(150, 190, 230, 0.5);
    border-radius: 10px;
    padding: 25px 30px;
    transition: all 0.4s ease;
  }

  section:hover {
    background: rgba(255,255,255,0.06);
    transform: translateY(-3px);
  }

  h2 {
    color: var(--accent);
    border-left: 6px solid var(--accent);
    padding-left: 10px;
    margin-bottom: 20px;
    transition: color 0.6s ease, border-color 0.6s ease;
  }

  strong { color: var(--accent-strong); }

  footer {
    position: relative;
    z-index: 2;
    background: var(--footer-bg);
    color: white;
    text-align: center;
    padding: 20px;
    font-size: 0.9em;
    letter-spacing: 0.5px;
    transition: background 0.6s ease;
  }

  /* --- Overlay ảnh Senna --- */
  #sennaOverlay {
    display: none;
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0,0,0,0.9);
    justify-content: center;
    align-items: center;
    z-index: 1500;
    opacity: 0;
    transition: opacity 0.6s ease;
  }
  #sennaOverlay.show { display: flex; opacity: 1; }
  #sennaOverlay img {
    max-width: 90%;
    max-height: 90%;
    border-radius: 10px;
    box-shadow: 0 0 30px rgba(255,255,255,0.3);
    transform: scale(0.8);
    opacity: 0;
    animation: zoomIn 0.6s ease forwards;
  }
  @keyframes zoomIn {
    from { transform: scale(0.8); opacity: 0; }
    to { transform: scale(1); opacity: 1; }
  }
</style>
</head>
<body>
  <canvas id="auroraCanvas"></canvas>

  <button id="modeToggle">🌙 Chế độ đêm</button>
  <button id="sennaButton">🏆 Senna</button>

  <header id="header">
    <div class="light-glow" id="light"></div>
    <h1 id="title">Trần Tất Đạt</h1>
    <p>Học sinh lớp 12 Hóa – Trường THPT Chuyên Hà Tĩnh</p>
  </header>

  <main>
    <section id="info">
      <h2>Phần 1: Thông tin cơ bản</h2>
      <ul>
        <li><strong>Họ và tên:</strong> Trần Tất Đạt</li>
        <li><strong>Lớp:</strong> 12 Hóa – Trường THPT Chuyên Hà Tĩnh</li>
        <li><strong>Nơi sinh:</strong> Tỉnh Hà Tĩnh</li>
        <li><strong>Ngày sinh:</strong> 12/03/2008</li>
      </ul>
    </section>

    <section id="hobby">
      <h2>Phần 2: Sở thích và tính cách</h2>
      <ul>
        <li><strong>Thời gian rảnh:</strong> Đọc tiểu thuyết</li>
        <li><strong>Môn yêu thích:</strong> Hóa học vì có Mr Hảo.</li>
        <li><strong>Ba từ miêu tả:</strong> .............</li>
        <li><strong>Thần tượng:</strong> Valentino Rossi, Ayrton Senna da Silva</li>
      </ul>
    </section>

    <section id="dream">
      <h2>Phần 3: Ước mơ và mục tiêu</h2>
      <ul>
        <li><strong>Muốn trở thành:</strong> Bác sĩ</li>
        <li><strong>Tự hào về:</strong> Đọc tiểu thuyết mạng 20 tiếng / ngày</li>
        <li><strong>Kỹ năng muốn học:</strong> Viết 2 tay</li>
      </ul>
    </section>
  </main>

  <footer>© TTĐ | Trang web cá nhân</footer>

  <div id="sennaOverlay">
    <img src="https://upload.wikimedia.org/wikipedia/commons/b/bf/Senna_1992_Monaco_cropped.jpg" alt="Ayrton Senna" />
  </div>

<script>
const canvas = document.getElementById("auroraCanvas");
const ctx = canvas.getContext("2d");
let w = canvas.width = window.innerWidth;
let h = canvas.height = window.innerHeight;
let mouse = { x: w/2, y: h/2 };
let dark = false;

// Dải aurora mềm
const auroras = Array.from({length: 5}, (_,i)=>({
  offset: Math.random()*Math.PI*2,
  color1: `hsla(${180+Math.random()*80},80%,60%,0.15)`,
  color2: `hsla(${220+Math.random()*80},80%,70%,0.15)`,
  speed: 0.002 + Math.random()*0.001
}));

function drawAurora(){
  if(!dark) { ctx.clearRect(0,0,w,h); requestAnimationFrame(drawAurora); return; }
  ctx.clearRect(0,0,w,h);
  auroras.forEach((a,i)=>{
    const grad = ctx.createLinearGradient(0, h*0.3*Math.sin(a.offset)+mouse.y*0.2, w, h*0.2*Math.cos(a.offset)+mouse.y*0.2);
    grad.addColorStop(0,a.color1);
    grad.addColorStop(1,a.color2);
    ctx.fillStyle = grad;
    ctx.beginPath();
    let amp = 80 + i*30;
    ctx.moveTo(0,h/2);
    for(let x=0; x<=w; x+=20){
      let y = h/2 + Math.sin(x*0.002 + a.offset)*amp*Math.sin(a.offset);
      y += (mouse.y-h/2)*0.05;
      ctx.lineTo(x,y);
    }
    ctx.lineTo(w,h); ctx.lineTo(0,h); ctx.closePath();
    ctx.fill();
    a.offset += a.speed;
  });
  requestAnimationFrame(drawAurora);
}

window.addEventListener("mousemove", e=>{
  mouse.x = e.clientX;
  mouse.y = e.clientY;
  const title = document.getElementById("title");
  const xRatio = e.clientX / w;
  const yRatio = e.clientY / h;
  title.style.textShadow = `
    0 0 20px rgba(100,200,255,${0.5 + 0.5*Math.abs(xRatio-0.5)}),
    0 0 40px rgba(200,150,255,${0.5 + 0.5*Math.abs(yRatio-0.5)})
  `;
});

window.addEventListener("resize",()=>{
  w = canvas.width = window.innerWidth;
  h = canvas.height = window.innerHeight;
});

const modeToggle = document.getElementById("modeToggle");
const sennaButton = document.getElementById("sennaButton");
const sennaOverlay = document.getElementById("sennaOverlay");

modeToggle.addEventListener("click",()=>{
  document.body.classList.toggle("dark");
  dark = !dark;
  modeToggle.textContent = dark ? "☀️ Chế độ sáng" : "🌙 Chế độ đêm";
});

sennaButton.addEventListener("click",()=>sennaOverlay.classList.add("show"));
sennaOverlay.addEventListener("click",()=>sennaOverlay.classList.remove("show"));

drawAurora();
</script>
</body>
</html>
