<style>
/* ❤️ Heartbeat Animation */
@keyframes heartbeat {
  0% { transform: scale(1); }
  30% { transform: scale(1.1); }
  50% { transform: scale(1); }
  70% { transform: scale(1.15); }
  100% { transform: scale(1); }
}

/* 🔘 Floating Button – RIGHT CENTER */
.floating-btn {
  position: fixed;
  top: 50%;
  right: 14px;
  transform: translateY(-50%);
  z-index: 9999;
  animation: heartbeat 1.8s infinite;
}

.floating-btn a {
  background: #1e90ff;
  color: #fff;
  padding: 6px 10px;
  border-radius: 16px;
  font-size: 11px;
  font-weight: 600;
  text-decoration: none;
  box-shadow: 0 2px 6px rgba(0,0,0,0.25);
}

/* 🪟 Modal Overlay */
#iframe-modal {
  display: none;
  position: fixed;
  inset: 0;
  background: rgba(0,0,0,0.75);
  backdrop-filter: blur(4px);
  z-index: 99999;
}

/* 📦 Modal Box */
.modal-box {
  position: relative;
  margin: 2% auto;
  width: 95%;
  height: 92%;
  background: #fff;
  border-radius: 16px;
  overflow: hidden;
}

/* 🧭 Toolbar */
.modal-toolbar {
  position: absolute;
  top: 8px;
  left: 10px;
  right: 10px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  z-index: 10;
}

.modal-toolbar button {
  background: #111;
  color: #fff;
  border: none;
  padding: 7px 10px;
  border-radius: 8px;
  font-size: 12px;
  cursor: pointer;
}

#modal-iframe {
  width: 100%;
  height: 100%;
  border: none;
}
</style>

<script>
document.addEventListener("DOMContentLoaded", function () {

  /* 🌐 WordPress Page */
  const pages = [
    "https://debeatzgh.wordpress.com/"
  ];

  let index = 0;

  /* 🔘 Floating Button */
  const floatBtn = document.createElement("div");
  floatBtn.className = "floating-btn";
  floatBtn.innerHTML = `<a href="#">🌐 Open</a>`;
  document.body.appendChild(floatBtn);

  /* 🪟 Modal */
  const modal = document.createElement("div");
  modal.id = "iframe-modal";
  modal.innerHTML = `
    <div class="modal-box">
      <div class="modal-toolbar">
        <div>
          <button id="prevBtn">◀</button>
          <button id="nextBtn">▶</button>
        </div>
        <button id="closeBtn">✖</button>
      </div>

      <iframe
        id="modal-iframe"
        loading="lazy"
        sandbox="allow-scripts allow-same-origin allow-popups allow-popups-to-escape-sandbox allow-forms allow-modals"
        allow="autoplay; encrypted-media; picture-in-picture"
        referrerpolicy="no-referrer-when-downgrade">
      </iframe>
    </div>
  `;
  document.body.appendChild(modal);

  const iframe = document.getElementById("modal-iframe");

  function openModal() {
    iframe.src = pages[index];
    modal.style.display = "block";
  }

  function closeModal() {
    modal.style.display = "none";
    iframe.src = "";
  }

  /* 🔘 Button Click ONLY */
  floatBtn.onclick = function (e) {
    e.preventDefault();
    openModal();
  };

  /* ⏭ Navigation (future ready) */
  document.getElementById("nextBtn").onclick = function () {
    index = (index + 1) % pages.length;
    openModal();
  };

  document.getElementById("prevBtn").onclick = function () {
    index = (index - 1 + pages.length) % pages.length;
    openModal();
  };

  /* ❌ Close */
  document.getElementById("closeBtn").onclick = closeModal;
  modal.onclick = e => e.target === modal && closeModal();

});
</script>


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
.hero h1{margin:0;font-size:2.5rem;}
.hero p{max-width:900px;margin:15px auto 0;}

/* CONTAINER */
.container{
  max-width:1100px;
  margin:auto;
  padding:25px;
}

/* SECTIONS */
.section{
  background:white;
  padding:25px;
  margin-bottom:30px;
  border-radius:14px;
  box-shadow:0 10px 30px rgba(0,0,0,0.05);
}
.section h2{color:var(--primary);}

/* BUTTON */
.btn{
  padding:10px 18px;
  background:var(--primary);
  color:white;
  border-radius:8px;
  border:none;
  cursor:pointer;
  font-size:0.9rem;
}

/* ===== CAROUSEL ===== */
.carousel{position:relative;overflow:hidden;}
.carousel-track{display:flex;transition:transform 0.6s ease;}
.slide{min-width:100%;padding:20px;}
.card{
  background:#f8fafc;
  padding:25px;
  border-radius:12px;
  box-shadow:0 6px 18px rgba(0,0,0,0.05);
}
.card h3{margin-top:0;color:#1d4ed8;}

.nav{
  position:absolute;
  top:50%;
  transform:translateY(-50%);
  background:#020617;
  color:white;
  border:none;
  font-size:18px;
  padding:10px 14px;
  cursor:pointer;
}
.prev{left:10px;}
.next{right:10px;}

/* ===== IFRAME POPUP ===== */
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

/* 🔘 Bottom Controls */
.viewer-controls{
  position:fixed;
  bottom:18px;
  left:50%;
  transform:translateX(-50%);
  display:flex;
  gap:14px;
  z-index:10000;
}

.control-btn{
  background:#020617;
  color:white;
  padding:12px 16px;
  border-radius:50%;
  font-size:18px;
  cursor:pointer;
}
.close-btn{background:#ef4444}

/* FLOATING BUTTON */
.floating{
  position:fixed;
  bottom:20px;
  right:20px;
  background:var(--primary);
  color:white;
  padding:14px 18px;
  border-radius:30px;
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
}
</style>
</head>

<body>

<!-- HERO -->
<div class="hero">
  <h1>Digital Creators Hub</h1>
  <p>Build AI-powered digital assets, startups & online income from scratch.</p>
</div>

<div class="container">

  <!-- SOCIALCREATOR CAROUSEL -->
  <div class="section">
    <h2>🌟 Featured Creator Resources</h2>

    <div class="carousel">
      <div class="carousel-track" id="track">

        <div class="slide"><div class="card">
          <h3>Work Smarter with AI</h3>
          <p>Boost productivity using AI-powered workflows.</p>
          <button class="btn" onclick="openDoc('https://docs.google.com/document/d/1D9_b4p374Av6KmnJu7WJ_-OdfUglaiNc/preview')">View</button>
        </div></div>

        <div class="slide"><div class="card">
          <h3>Build a Tech Business</h3>
          <p>Everything needed to start a tech company.</p>
          <button class="btn" onclick="openDoc('https://docs.google.com/document/d/1_vtKBb2IFPjPoGPlzSfbYdOPQKocy5kg/preview')">View</button>
        </div></div>

        <div class="slide"><div class="card">
          <h3>Online Store Setup</h3>
          <p>No skills required to start selling online.</p>
          <button class="btn" onclick="openDoc('https://docs.google.com/document/d/1zwmOqkbaUtWm-o-Sgr6Wqmto5Irlmnsr/preview')">View</button>
        </div></div>

        <div class="slide"><div class="card">
          <h3>Side Hustle from Scratch</h3>
          <p>Turn ideas into income streams.</p>
          <button class="btn" onclick="openDoc('https://docs.google.com/document/d/1nkIOxY4vhtCtZT2eJJHFqlGUypMUWTkB/preview')">View</button>
        </div></div>

      </div>

      <button class="nav prev" onclick="prevSlide()">‹</button>
      <button class="nav next" onclick="nextSlide()">›</button>
    </div>
  </div>

</div>

<!-- IFRAME VIEWER -->
<div id="viewer">
  <iframe id="docFrame"></iframe>

  <!-- Bottom Middle Controls -->
  <div class="viewer-controls">
    <div class="control-btn" onclick="toggleFullscreen()">⛶</div>
    <div class="control-btn close-btn" onclick="closeDoc()">✕</div>
  </div>
</div>

<!-- FLOATING SUPPORT -->
<div class="floating" onclick="openDoc('https://form.jotform.com/241335470278053')">
  💬 Get Support
</div>

<footer>
  <p>© Digital Creators Hub – Debeatzgh</p>
</footer>

<script>
/* IFRAME */
function openDoc(url){
  document.getElementById('docFrame').src = url;
  document.getElementById('viewer').style.display = 'block';
}
function closeDoc(){
  document.getElementById('docFrame').src = '';
  document.getElementById('viewer').style.display = 'none';
}

/* FULLSCREEN */
function toggleFullscreen(){
  const v = document.getElementById('viewer');
  if(!document.fullscreenElement){
    v.requestFullscreen().catch(()=>{});
  }else{
    document.exitFullscreen();
  }
}

/* AUTO OPEN */
window.onload = () => {
  setTimeout(() => {
    openDoc('https://docs.google.com/document/d/1D9_b4p374Av6KmnJu7WJ_-OdfUglaiNc/preview');
  }, 1500);
};

/* CAROUSEL */
let index=0;
const track=document.getElementById('track');
const slides=document.querySelectorAll('.slide');
function updateSlide(){track.style.transform=`translateX(-${index*100}%)`;}
function nextSlide(){index=(index+1)%slides.length;updateSlide();}
function prevSlide(){index=(index-1+slides.length)%slides.length;updateSlide();}
setInterval(nextSlide,5000);
</script>

</body>
</html>
