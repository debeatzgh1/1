
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Digital Creators Hub – All-in-One AI Platform</title>

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
.hero{
  background:linear-gradient(135deg,var(--primary),var(--secondary));
  color:#fff;
  padding:60px 20px;
  text-align:center;
}
.container{max-width:1200px;margin:auto;padding:25px;}
.section{
  background:#fff;
  padding:25px;
  margin-bottom:30px;
  border-radius:14px;
  box-shadow:0 10px 30px rgba(0,0,0,.05);
}
.section h2{color:var(--primary);}
.grid{
  display:grid;
  grid-template-columns:repeat(auto-fit,minmax(260px,1fr));
  gap:20px;
}
.card{
  background:#f8fafc;
  padding:20px;
  border-radius:12px;
}
.btn{
  margin-top:10px;
  padding:10px 16px;
  background:var(--primary);
  color:white;
  border:none;
  border-radius:8px;
  cursor:pointer;
  font-size:.9rem;
}

/* IFRAME VIEWER */
#viewer{
  position:fixed;
  inset:0;
  background:rgba(0,0,0,.85);
  display:none;
  z-index:9999;
}
#viewer iframe{width:100%;height:100%;border:none;}
.control{
  position:absolute;
  top:15px;
  padding:10px 14px;
  border-radius:50%;
  cursor:pointer;
  color:white;
  z-index:10000;
}
#closeBtn{left:15px;background:#ef4444;}
#fullscreenBtn{right:15px;background:#020617;}

/* FLOATING */
@keyframes heartbeat{0%{transform:scale(1)}14%{transform:scale(1.15)}28%{transform:scale(1)}}
@keyframes bubble{0%{box-shadow:0 0 0 0 rgba(37,99,235,.6)}70%{box-shadow:0 0 0 25px rgba(37,99,235,0)}}
.floating{
  position:fixed;
  bottom:20px;
  right:20px;
  background:var(--primary);
  color:white;
  padding:14px 18px;
  border-radius:30px;
  cursor:pointer;
  animation:heartbeat 2.5s infinite,bubble 3s infinite;
  z-index:9998;
}
footer{
  background:#020617;
  color:#cbd5f5;
  padding:30px;
  text-align:center;
}
</style>
</head>

<body>

<div class="hero">
  <h1>Digital Creators Hub</h1>
  <p>Treasure troves for startups, creators & entrepreneurs building successful digital assets from scratch using AI.</p>
</div>

<div class="container">

<div class="section">
<h2>🌟 Core Programs & Guides</h2>
<div class="grid">

<div class="card">
<h3>How to Work Smarter with AI</h3>
<p>Boost productivity using artificial intelligence.</p>
<button class="btn" onclick="openSmart('https://docs.google.com/document/d/1D9_b4p374Av6KmnJu7WJ_-OdfUglaiNc/preview')">Open</button>
</div>

<div class="card">
<h3>Tech Business Tools & Ideas</h3>
<p>Everything you need to build a tech startup.</p>
<button class="btn" onclick="openSmart('https://docs.google.com/document/d/1_vtKBb2IFPjPoGPlzSfbYdOPQKocy5kg/preview')">Open</button>
</div>

<div class="card">
<h3>Own an Online Store</h3>
<p>Anyone can start selling online.</p>
<button class="btn" onclick="openSmart('https://docs.google.com/document/d/1zwmOqkbaUtWm-o-Sgr6Wqmto5Irlmnsr/preview')">Open</button>
</div>

<div class="card">
<h3>AI Marketing Agency</h3>
<p>Start or collaborate on AI-driven marketing.</p>
<button class="btn" onclick="openSmart('https://docs.google.com/document/d/1HS-a0SsGU7VfCtbuhOvUoHYYPwhDKlBw/preview')">Open</button>
</div>

<div class="card">
<h3>Work From Home Tools</h3>
<p>Build digital assets with or without skills.</p>
<button class="btn" onclick="openSmart('https://docs.google.com/document/d/1m09Dby3ZPvU_MXjTXCBvDvZO-iNm5c2E/preview')">Open</button>
</div>

<div class="card">
<h3>Start an Online Business</h3>
<p>Learn different online business models.</p>
<button class="btn" onclick="openSmart('https://docs.google.com/document/d/1bEOxMCEmWALqqB0PUtaUxjA1-Wevdy1o/preview')">Open</button>
</div>

<div class="card">
<h3>Become a Digital Creator</h3>
<p>Turn creativity into income.</p>
<button class="btn" onclick="openSmart('https://docs.google.com/document/d/1cfdz8HYxl8xzXWMA1KovKRcLAiwFn-gU/preview')">Open</button>
</div>

<div class="card">
<h3>Freelancing Tools & Ideas</h3>
<p>Work independently and choose your projects.</p>
<button class="btn" onclick="openSmart('https://docs.google.com/document/d/1gZf-sA8TS6EhZPzBSyQjCtIE2BSlWANU/preview')">Open</button>
</div>

<div class="card">
<h3>Blogging from Scratch</h3>
<p>Start and grow a profitable blog.</p>
<button class="btn" onclick="openSmart('https://docs.google.com/document/d/19qAFHPNvb3ZGcJAUS1dUgiq-fSJLQmoF/preview')">Open</button>
</div>

<div class="card">
<h3>Affiliate Marketing</h3>
<p>Earn commissions promoting products.</p>
<button class="btn" onclick="openSmart('https://docs.google.com/document/d/1Z4dIhaLH-tXA0NCDngKezPMJ6e3mYa9t/preview')">Open</button>
</div>

<div class="card">
<h3>Side Hustle from Scratch</h3>
<p>Build extra income streams.</p>
<button class="btn" onclick="openSmart('https://docs.google.com/document/d/1nkIOxY4vhtCtZT2eJJHFqlGUypMUWTkB/preview')">Open</button>
</div>

<div class="card">
<h3>Productivity Tools with AI</h3>
<p>Stand out using AI-powered workflows.</p>
<button class="btn" onclick="openSmart('https://docs.google.com/document/d/1yTeRMaF8GEkTZf34EK7eOdxe6sCOCNxX/preview')">Open</button>
</div>

</div>
</div>

</div>

<!-- IFRAME VIEWER -->
<div id="viewer">
  <div id="closeBtn" class="control" onclick="closeDoc()">✕</div>
  <div id="fullscreenBtn" class="control" onclick="toggleFullscreen()">⛶</div>
  <iframe id="docFrame"></iframe>
</div>

<div class="floating" onclick="openSmart('https://tally.so/r/3lWJZV')">💬 Get Support</div>

<footer>
  <p>© Digital Creators Hub – Debeatzgh</p>
</footer>

<script>
function openSmart(url){
  const frame=document.getElementById('docFrame');
  frame.src=url;
  document.getElementById('viewer').style.display='block';
  setTimeout(()=>{
    try{
      if(!frame.contentDocument || frame.contentDocument.body.innerHTML.length<50){
        window.open(url,'_blank');
        closeDoc();
      }
    }catch(e){
      window.open(url,'_blank');
      closeDoc();
    }
  },1200);
}
function closeDoc(){
  document.getElementById('docFrame').src='';
  document.getElementById('viewer').style.display='none';
  if(document.fullscreenElement) document.exitFullscreen();
}
function toggleFullscreen(){
  const viewer=document.getElementById('viewer');
  if(!document.fullscreenElement){
    viewer.requestFullscreen().catch(()=>{});
  }else{
    document.exitFullscreen();
  }
}
</script>

</body>
</html>
