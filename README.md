
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Digital Creators Hub – Build With AI</title>

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
  color:white;
  padding:70px 20px;
  text-align:center;
}
.hero h1{margin:0;font-size:2.6rem}
.hero p{max-width:900px;margin:15px auto;font-size:1.1rem}

/* LAYOUT */
.container{max-width:1200px;margin:auto;padding:30px}
.section{
  background:white;
  padding:28px;
  margin-bottom:30px;
  border-radius:16px;
  box-shadow:0 12px 35px rgba(0,0,0,.06);
}
.section h2{color:var(--primary);margin-top:0}

.grid{
  display:grid;
  grid-template-columns:repeat(auto-fit,minmax(260px,1fr));
  gap:22px;
}
.card{
  background:#f8fafc;
  padding:22px;
  border-radius:14px;
}

/* BUTTONS (LIVE) */
@keyframes heartbeat{0%{transform:scale(1)}14%{transform:scale(1.15)}28%{transform:scale(1)}}
@keyframes shake{0%,100%{transform:translateX(0)}25%{transform:translateX(-2px)}75%{transform:translateX(2px)}}

.btn{
  display:inline-block;
  margin-top:12px;
  padding:10px 18px;
  background:var(--primary);
  color:white;
  border-radius:8px;
  text-decoration:none;
  font-size:.9rem;
  cursor:pointer;
  animation:heartbeat 2.8s infinite, shake 6s infinite;
}

/* IFRAME VIEWER */
#viewer{
  position:fixed;
  inset:0;
  background:rgba(0,0,0,.88);
  display:none;
  z-index:9999;
}
#viewer iframe{width:100%;height:100%;border:none}

.control{
  position:absolute;
  top:15px;
  background:#020617;
  color:white;
  padding:10px 14px;
  border-radius:50%;
  cursor:pointer;
  z-index:10000;
}
#closeBtn{left:15px;background:#ef4444}
#backBtn{left:70px}
#forwardBtn{left:125px}
#fullscreenBtn{right:15px}

/* FOOTER */
footer{
  background:#020617;
  color:#cbd5f5;
  padding:35px;
  text-align:center;
}
</style>
</head>

<body>

<!-- HERO -->
<div class="hero">
  <h1>Digital Creators Hub</h1>
  <p>
    Treasure troves for startups, creators, and entrepreneurs who want to build
    successful digital assets and online presence from scratch.
  </p>
</div>

<div class="container">

<!-- ABOUT / AI -->
<div class="section">
<h2>🤖 Build With AI & Assistant Bot</h2>
<p>
Improve your research, productivity, and decision-making using our AI-powered assistant
built to support students, creators, and businesses.
</p>
<button class="btn" onclick="openSmart('https://docs.google.com/document/d/1Kz1DaFDuigCiV62K7LH6Iugcl-rSgvtW/preview')">
Learn About AI
</button>
</div>

<!-- TOP CONTENTS -->
<div class="section">
<h2>🔥 Top AI & Productivity Guides</h2>
<div class="grid">

<div class="card">
<h3>Work Smarter, Not Harder with AI</h3>
<p>A comprehensive guide on boosting productivity using AI.</p>
<button class="btn" onclick="openSmart('https://docs.google.com/document/d/1D9_b4p374Av6KmnJu7WJ_-OdfUglaiNc/preview')">
Read Guide
</button>
</div>

<div class="card">
<h3>Productivity Tools & Ideas</h3>
<p>Stand out from generic startups using AI-powered workflows.</p>
<button class="btn" onclick="openSmart('https://docs.google.com/document/d/1yTeRMaF8GEkTZf34EK7eOdxe6sCOCNxX/preview')">
Learn More
</button>
</div>

</div>
</div>

<!-- STARTUP & BUSINESS -->
<div class="section">
<h2>🚀 Start & Grow Digital Businesses</h2>
<div class="grid">

<div class="card">
<h3>Tech Business Tools & Ideas</h3>
<p>Everything you need to build a tech business from scratch.</p>
<button class="btn" onclick="openSmart('https://docs.google.com/document/d/1_vtKBb2IFPjPoGPlzSfbYdOPQKocy5kg/preview')">
Explore
</button>
</div>

<div class="card">
<h3>Own an Online Store</h3>
<p>Anyone can own an online store — no experience required.</p>
<button class="btn" onclick="openSmart('https://docs.google.com/document/d/1zwmOqkbaUtWm-o-Sgr6Wqmto5Irlmnsr/preview')">
Learn How
</button>
</div>

<div class="card">
<h3>Start an AI Marketing Agency</h3>
<p>Collaborate or launch your own AI-driven marketing agency.</p>
<button class="btn" onclick="openSmart('https://docs.google.com/document/d/1HS-a0SsGU7VfCtbuhOvUoHYYPwhDKlBw/preview')">
Get Started
</button>
</div>

</div>
</div>

<!-- CREATOR ECONOMY -->
<div class="section">
<h2>🎨 Creator, Freelancing & Side Hustles</h2>
<div class="grid">

<div class="card">
<h3>Become a Digital Creator</h3>
<p>Steps to start creating content and building influence online.</p>
<button class="btn" onclick="openSmart('https://docs.google.com/document/d/1cfdz8HYxl8xzXWMA1KovKRcLAiwFn-gU/preview')">
Learn More
</button>
</div>

<div class="card">
<h3>Freelancing Tools & Ideas</h3>
<p>Work independently and choose projects you love.</p>
<button class="btn" onclick="openSmart('https://docs.google.com/document/d/1gZf-sA8TS6EhZPzBSyQjCtIE2BSlWANU/preview')">
Explore
</button>
</div>

<div class="card">
<h3>Build a Side Hustle</h3>
<p>Turn extra income ideas into real businesses.</p>
<button class="btn" onclick="openSmart('https://docs.google.com/document/d/1nkIOxY4vhtCtZT2eJJHFqlGUypMUWTkB/preview')">
Start Now
</button>
</div>

</div>
</div>

<!-- BLOGGING & AFFILIATE -->
<div class="section">
<h2>📝 Blogging & Affiliate Marketing</h2>
<div class="grid">

<div class="card">
<h3>Start Blogging From Scratch</h3>
<p>Blogging is alive — learn how to do it right.</p>
<button class="btn" onclick="openSmart('https://docs.google.com/document/d/19qAFHPNvb3ZGcJAUS1dUgiq-fSJLQmoF/preview')">
Read Guide
</button>
</div>

<div class="card">
<h3>Affiliate Marketing</h3>
<p>Earn commissions promoting other companies’ products.</p>
<button class="btn" onclick="openSmart('https://docs.google.com/document/d/1Z4dIhaLH-tXA0NCDngKezPMJ6e3mYa9t/preview')">
Learn More
</button>
</div>

</div>
</div>

<!-- UPDATES -->
<div class="section">
<h2>📢 Latest Updates</h2>
<p>Content announcements, side hustle ideas, and new opportunities.</p>
<button class="btn" onclick="openSmart('https://docs.google.com/document/d/137INFWxQI8-i01-R3vt1CXFi3QevmbhW/preview')">
Read Updates
</button>
</div>

</div>

<!-- VIEWER -->
<div id="viewer">
  <div id="closeBtn" class="control" onclick="closeViewer()">✕</div>
  <div id="backBtn" class="control" onclick="goBack()">⟵</div>
  <div id="forwardBtn" class="control" onclick="goForward()">⟶</div>
  <div id="fullscreenBtn" class="control" onclick="toggleFullscreen()">⛶</div>
  <iframe id="docFrame"></iframe>
</div>

<footer>
<p>© Digital Creators Hub – Debeatzgh</p>
<p>Build • Learn • Monetize with AI</p>
</footer>

<script>
let historyStack=[],historyIndex=-1;

function openSmart(url){
  document.getElementById('viewer').style.display='block';
  loadUrl(url,true);
  setTimeout(()=>{
    const f=document.getElementById('docFrame');
    try{
      if(!f.contentDocument || f.contentDocument.body.innerHTML.length<50){
        window.open(url,'_blank'); closeViewer();
      }
    }catch(e){
      window.open(url,'_blank'); closeViewer();
    }
  },1200);
}

function loadUrl(url,push){
  document.getElementById('docFrame').src=url;
  if(push){
    historyStack=historyStack.slice(0,historyIndex+1);
    historyStack.push(url);
    historyIndex++;
  }
}
function goBack(){if(historyIndex>0){historyIndex--;loadUrl(historyStack[historyIndex],false)}}
function goForward(){if(historyIndex<historyStack.length-1){historyIndex++;loadUrl(historyStack[historyIndex],false)}}
function toggleFullscreen(){
  const v=document.getElementById('viewer');
  if(!document.fullscreenElement){v.requestFullscreen().catch(()=>{})}
  else{document.exitFullscreen()}
}
function closeViewer(){
  document.getElementById('viewer').style.display='none';
  document.getElementById('docFrame').src='';
}
</script>

</body>
</html>
