
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Digital Creators Hub – Build with AI</title>

<style>
:root{
  --primary:#2563eb;
  --secondary:#16a34a;
  --dark:#020617;
  --light:#f8fafc;
}

body{
  margin:0;
  font-family:system-ui, Arial, sans-serif;
  background:#f1f5f9;
  color:#1e293b;
}

/* HERO */
.hero{
  background:linear-gradient(135deg,var(--primary),var(--secondary));
  color:white;
  padding:60px 20px;
  text-align:center;
}
.hero h1{
  font-size:2.5rem;
  margin:0;
}
.hero p{
  max-width:900px;
  margin:15px auto 0;
  font-size:1.1rem;
}

/* SECTIONS */
.container{
  max-width:1100px;
  margin:auto;
  padding:25px;
}
.section{
  background:white;
  padding:25px;
  margin-bottom:25px;
  border-radius:14px;
  box-shadow:0 10px 30px rgba(0,0,0,0.05);
}
.section h2{
  color:var(--primary);
  margin-top:0;
}

/* GRID */
.grid{
  display:grid;
  grid-template-columns:repeat(auto-fit,minmax(260px,1fr));
  gap:20px;
}

/* BUTTONS */
.btn{
  display:inline-block;
  padding:10px 18px;
  background:var(--primary);
  color:white;
  border-radius:8px;
  text-decoration:none;
  font-size:0.9rem;
  margin-top:10px;
  cursor:pointer;
}
.btn.secondary{ background:var(--secondary); }

/* IFRAME MODAL */
#viewer{
  position:fixed;
  inset:0;
  background:rgba(0,0,0,0.85);
  display:none;
  z-index:9999;
}
#viewer iframe{
  width:100%;
  height:100%;
  border:none;
}
#closeBtn{
  position:absolute;
  top:15px;
  left:15px;
  background:#ef4444;
  color:white;
  padding:10px 14px;
  border-radius:50%;
  font-size:16px;
  cursor:pointer;
  z-index:10000;
}

/* FLOATING BUTTON */
.floating{
  position:fixed;
  bottom:20px;
  right:20px;
  background:var(--primary);
  color:white;
  padding:14px 18px;
  border-radius:30px;
  font-size:14px;
  box-shadow:0 10px 30px rgba(0,0,0,0.3);
  cursor:pointer;
  z-index:9998;
}

/* FOOTER */
footer{
  background:#020617;
  color:#cbd5f5;
  padding:30px;
  text-align:center;
  font-size:0.9rem;
}
</style>
</head>

<body>

<!-- HERO -->
<div class="hero">
  <h1>Digital Creators Hub</h1>
  <p>Treasure troves for startups, creators & entrepreneurs building AI-powered digital assets from scratch.</p>
</div>

<!-- CONTENT -->
<div class="container">

  <div class="section">
    <h2>🔥 Top AI Guide</h2>
    <p><strong>How to Work Smarter, Not Harder with AI</strong></p>
    <button class="btn" onclick="openDoc('https://msha.ke/debeatzgh')">
      View in Page
    </button>
  </div>

  <div class="section">
    <h2>📌 Explore Opportunities</h2>
    <div class="grid">

      <div>
        <h3>Tech Business Tools</h3>
        <p>Everything you need to build a tech startup.</p>
        <button class="btn" onclick="openDoc('https://docs.google.com/document/d/1_vtKBb2IFPjPoGPlzSfbYdOPQKocy5kg/preview')">View</button>
      </div>

      <div>
        <h3>Own an Online Store</h3>
        <p>No experience needed to start selling online.</p>
        <button class="btn" onclick="openDoc('https://docs.google.com/document/d/1zwmOqkbaUtWm-o-Sgr6Wqmto5Irlmnsr/preview')">View</button>
      </div>

      <div>
        <h3>AI Marketing Agency</h3>
        <p>Launch or collaborate in AI-driven marketing.</p>
        <button class="btn" onclick="openDoc('https://docs.google.com/document/d/1HS-a0SsGU7VfCtbuhOvUoHYYPwhDKlBw/preview')">View</button>
      </div>

      <div>
        <h3>Side Hustle from Scratch</h3>
        <p>Turn ideas into extra income streams.</p>
        <button class="btn" onclick="openDoc('https://docs.google.com/document/d/1nkIOxY4vhtCtZT2eJJHFqlGUypMUWTkB/preview')">View</button>
      </div>

      <div>
        <h3>Affiliate Marketing</h3>
        <p>Earn commissions promoting products.</p>
        <button class="btn" onclick="openDoc('https://docs.google.com/document/d/1Z4dIhaLH-tXA0NCDngKezPMJ6e3mYa9t/preview')">View</button>
      </div>

      <div>
        <h3>Productivity with AI</h3>
        <p>Stand out using AI-powered workflows.</p>
        <button class="btn" onclick="openDoc('https://docs.google.com/document/d/1yTeRMaF8GEkTZf34EK7eOdxe6sCOCNxX/preview')">View</button>
      </div>

    </div>
  </div>

</div>

<!-- IFRAME VIEWER -->
<div id="viewer">
  <div id="closeBtn" onclick="closeDoc()">✕</div>
  <iframe id="docFrame"></iframe>
</div>

<!-- FLOATING BUTTON -->
<div class="floating" onclick="openDoc('https://form.jotform.com/241335470278053')">
  💬 Get Support
</div>

<!-- FOOTER -->
<footer>
  <p>© Digital Creators Hub – Debeatzgh</p>
  <p>Build • Learn • Monetize with AI</p>
</footer>

<script>
function openDoc(url){
  document.getElementById('docFrame').src = url;
  document.getElementById('viewer').style.display = 'block';
}
function closeDoc(){
  document.getElementById('docFrame').src = '';
  document.getElementById('viewer').style.display = 'none';
}
</script>

</body>
</html>
