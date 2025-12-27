<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Digital Creators Hub – AI Powered</title>

<style>
:root{
  --primary:#2563eb;
  --secondary:#16a34a;
  --dark:#020617;
}

body{
  margin:0;
  font-family:system-ui,Arial,sans-serif;
  background:#f1f5f9;
  color:#1e293b;
}

/* HERO */
.hero{
  background:linear-gradient(135deg,var(--primary),var(--secondary));
  color:#fff;
  padding:60px 20px;
  text-align:center;
}

/* LAYOUT */
.container{max-width:1100px;margin:auto;padding:25px;}
.section{
  background:#fff;
  padding:25px;
  margin-bottom:30px;
  border-radius:14px;
  box-shadow:0 10px 30px rgba(0,0,0,.05);
}

/* BADGES */
.badge{
  display:inline-block;
  font-size:11px;
  padding:4px 8px;
  border-radius:6px;
  margin-right:5px;
  color:#fff;
}
.ai{background:#6366f1;}
.popular{background:#f59e0b;}
.new{background:#16a34a;}
.guide{background:#0ea5e9;}

/* BUTTON */
.btn{
  background:var(--primary);
  color:white;
  padding:10px 16px;
  border-radius:8px;
  border:none;
  cursor:pointer;
  font-size:.9rem;
}

/* ===== CAROUSEL ===== */
.carousel{position:relative;overflow:hidden;}
.track{display:flex;transition:.6s ease;}
.slide{min-width:100%;padding:10px;}
.card{
  background:#f8fafc;
  padding:25px;
  border-radius:12px;
}

/* NAV */
.nav{
  position:absolute;
  top:50%;
  transform:translateY(-50%);
  background:#020617;
  color:white;
  padding:10px;
  border:none;
  cursor:pointer;
}
.prev{left:10px;}
.next{right:10px;}

/* ===== IFRAME VIEWER ===== */
#viewer{
  position:fixed;
  inset:0;
  background:rgba(0,0,0,.85);
  display:none;
  z-index:9999;
}
#viewer iframe{
  width:100%;
  height:100%;
  border:none;
}
#close{
  position:absolute;
  top:15px;
  left:15px;
  background:#ef4444;
  color:white;
  padding:10px 14px;
  border-radius:50%;
  cursor:pointer;
}

/* FLOATING OVERLAY */
.floating{
  position:fixed;
  bottom:20px;
  right:20px;
  background:var(--primary);
  color:white;
  padding:14px 18px;
  border-radius:30px;
  cursor:pointer;
  box-shadow:0 10px 30px rgba(0,0,0,.3);
  z-index:9998;
}
.menu{
  position:fixed;
  bottom:80px;
  right:20px;
  background:white;
  padding:15px;
  border-radius:12px;
  display:none;
  box-shadow:0 10px 30px rgba(0,0,0,.2);
}
.menu button{
  display:block;
  width:100%;
  margin-bottom:10px;
}
</style>
</head>

<body>

<div class="hero">
  <h1>Digital Creators Hub</h1>
  <p>AI-powered tools, guides & digital assets for startups and creators</p>
</div>

<div class="container">

  <!-- SOCIALCREATOR CAROUSEL -->
  <div class="section">
    <h2>🌟 Featured Resources</h2>
    <div class="carousel">
      <div class="track" id="track">

        <div class="slide">
          <div class="card">
            <span class="badge ai">AI</span><span class="badge popular">Popular</span>
            <h3>Work Smarter with AI</h3>
            <button class="btn" onclick="openSmart('https://docs.google.com/document/d/1D9_b4p374Av6KmnJu7WJ_-OdfUglaiNc/preview')">Open</button>
          </div>
        </div>

        <div class="slide">
          <div class="card">
            <span class="badge guide">Guide</span>
            <h3>Build Tech Business</h3>
            <button class="btn" onclick="openSmart('https://docs.google.com/document/d/1_vtKBb2IFPjPoGPlzSfbYdOPQKocy5kg/preview')">Open</button>
          </div>
        </div>

      </div>
      <button class="nav prev" onclick="prev()">‹</button>
      <button class="nav next" onclick="next()">›</button>
    </div>
  </div>

</div>

<!-- IFRAME VIEWER -->
<div id="viewer">
  <div id="close" onclick="closeViewer()">✕</div>
  <iframe id="frame"></iframe>
</div>

<!-- FLOATING OVERLAY -->
<div class="floating" onclick="toggleMenu()">☰ Open</div>
<div class="menu" id="menu">
  <button class="btn" onclick="openSmart('https://tally.so/r/3lWJZV')">Support</button>
  <button class="btn" onclick="openSmart('https://docs.google.com/document/d/1D9_b4p374Av6KmnJu7WJ_-OdfUglaiNc/preview')">Docs</button>
  <button class="btn" onclick="openSmart('https://debeatzgh1.github.io/ai-chat/')">AI Assistant</button>
</div>

<script>
/* SMART IFRAME OPEN */
function openSmart(url){
  const frame=document.getElementById('frame');
  frame.src=url;
  document.getElementById('viewer').style.display='block';

  setTimeout(()=>{
    try{
      if(frame.contentDocument===null){
        window.open(url,'_blank');
        closeViewer();
      }
    }catch(e){
      window.open(url,'_blank');
      closeViewer();
    }
  },1500);
}
function closeViewer(){
  document.getElementById('frame').src='';
  document.getElementById('viewer').style.display='none';
}

/* FLOATING MENU */
function toggleMenu(){
  const m=document.getElementById('menu');
  m.style.display=m.style.display==='block'?'none':'block';
}

/* CAROUSEL */
let i=0;
const slides=document.querySelectorAll('.slide');
const track=document.getElementById('track');
function update(){track.style.transform=`translateX(-${i*100}%)`;}
function next(){i=(i+1)%slides.length;update();}
function prev(){i=(i-1+slides.length)%slides.length;update();}
setInterval(next,5000);
</script>

</body>
</html>
