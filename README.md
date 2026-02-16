
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        :root {
            --banner-bg: rgba(13, 17, 23, 0.85);
            --accent-pink: #FF1493;
            --accent-glow: rgba(255, 20, 147, 0.4);
            --text-white: #ffffff;
            --border-glass: rgba(255, 255, 255, 0.1);
        }

        /* Floating Banner Container */
        .top-floating-banner {
            position: fixed;
            top: 15px;
            left: 50%;
            transform: translateX(-50%);
            width: 90%;
            max-width: 700px;
            height: 50px;
            background: var(--banner-bg);
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px);
            border: 1px solid var(--border-glass);
            border-radius: 100px;
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 0 10px 0 25px;
            z-index: 10000;
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.5);
            overflow: hidden;
            animation: slideDown 0.8s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        }

        /* Carousel Wrapper */
        .carousel-wrapper {
            flex: 1;
            overflow: hidden;
            position: relative;
            margin-right: 15px;
        }

        .carousel-content {
            display: flex;
            white-space: nowrap;
            animation: scrollText 15s linear infinite;
        }

        .carousel-content span {
            font-family: 'Segoe UI', Roboto, sans-serif;
            font-size: 0.85rem;
            color: var(--text-white);
            font-weight: 500;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        /* Launch Button */
        .banner-btn {
            background: var(--accent-pink);
            color: white;
            border: none;
            padding: 8px 20px;
            border-radius: 50px;
            font-size: 0.8rem;
            font-weight: 700;
            cursor: pointer;
            transition: all 0.3s ease;
            display: flex;
            align-items: center;
            gap: 6px;
            box-shadow: 0 0 15px var(--accent-glow);
            text-transform: uppercase;
            letter-spacing: 0.5px;
        }

        .banner-btn:hover {
            transform: scale(1.05);
            background: #ff69b4;
            box-shadow: 0 0 25px var(--accent-glow);
        }

        /* Modal Overlay for Milkshake */
        #milkshake-modal {
            position: fixed;
            inset: 0;
            background: rgba(0, 0, 0, 0.9);
            display: none;
            z-index: 10001;
            flex-direction: column;
            animation: fadeIn 0.3s ease;
        }

        .modal-header {
            padding: 15px 25px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            background: #161b22;
        }

        .close-btn {
            background: #f85149;
            color: white;
            border: none;
            padding: 5px 15px;
            border-radius: 5px;
            cursor: pointer;
            font-weight: bold;
        }

        #msha-iframe {
            width: 100%;
            flex-grow: 1;
            border: none;
        }

        /* Animations */
        @keyframes scrollText {
            0% { transform: translateX(100%); }
            100% { transform: translateX(-100%); }
        }

        @keyframes slideDown {
            from { transform: translate(-50%, -100px); opacity: 0; }
            to { transform: translate(-50%, 0); opacity: 1; }
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        /* Mobile Adjustments */
        @media (max-width: 600px) {
            .carousel-content span { font-size: 0.75rem; }
            .banner-btn span { display: none; }
            .banner-btn { padding: 8px 12px; }
        }
    </style>
</head>
<body>

    <div class="top-floating-banner">
        <div class="carousel-wrapper">
            <div class="carousel-content">
                <span>
                    💻 Access your lifestyle, productivity tools and ideas All in one place! 🚀 💡 📈
                </span>
            </div>
        </div>
        
        <button class="banner-btn" onclick="openMilkshake()">
            <span>Launch Hub</span> ⭐️
        </button>
    </div>

    <div id="milkshake-modal">
        <div class="modal-header">
            <span style="color:white; font-family: sans-serif; font-weight: bold;">Debeatzgh Hub</span>
            <button class="close-btn" onclick="closeMilkshake()">✕ Close</button>
        </div>
        <iframe id="msha-iframe" src=""></iframe>
    </div>

    <script>
        function openMilkshake() {
            const modal = document.getElementById('milkshake-modal');
            const iframe = document.getElementById('msha-iframe');
            
            // Set source only when clicked to save performance
            iframe.src = "https://msha.ke/debeatzgh";
            modal.style.display = "flex";
            document.body.style.overflow = "hidden"; // Disable scroll
        }

        function closeMilkshake() {
            const modal = document.getElementById('milkshake-modal');
            const iframe = document.getElementById('msha-iframe');
            
            modal.style.display = "none";
            iframe.src = ""; // Stop the iframe content
            document.body.style.overflow = "auto"; // Re-enable scroll
        }
    </script>

</body>
</html>




<html lang="en">
<head>
    <meta charset="UTF-8">
    <style>
        :root {
            --nav-bg: rgba(13, 17, 23, 0.95);
            --nav-border: #30363d;
            /* Changed to Deep Pink */
            --nav-accent: #FF1493; 
            --nav-hover: #FF69B4;
            --glow-color: rgba(255, 20, 147, 0.5);
        }

        /* Dock Container */
        .nav-dock {
            position: fixed;
            right: 20px;
            top: 50%;
            transform: translateY(-50%);
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 15px;
            z-index: 10000;
            font-family: sans-serif;
        }

        /* Launcher Button */
        #nav-launcher {
            width: 42px;
            height: 42px;
            background: var(--nav-bg);
            border: 2px solid var(--nav-border);
            color: var(--nav-accent);
            border-radius: 12px;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            backdrop-filter: blur(8px);
            transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
            box-shadow: 0 4px 15px rgba(0,0,0,0.4);
            padding: 0;
        }

        #nav-launcher.open {
            color: white;
            background: var(--nav-accent);
            border-color: var(--nav-accent);
            transform: rotate(-180deg);
        }

        /* Button Group */
        .nav-group {
            display: flex;
            flex-direction: column;
            gap: 12px;
            visibility: hidden;
            pointer-events: none;
        }

        .nav-group.active {
            visibility: visible;
            pointer-events: auto;
        }

        .nav-btn {
            width: 38px;
            height: 38px;
            background: var(--nav-bg);
            border: 1px solid var(--nav-border);
            color: #c9d1d9;
            border-radius: 50%;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            opacity: 0;
            transform: scale(0.5) translateX(40px);
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            text-decoration: none;
        }

        /* Active State for Buttons */
        .nav-group.active .nav-btn {
            opacity: 1;
            transform: scale(1) translateX(0);
        }

        /* Heartbeat Glow Animation */
        @keyframes heartbeatGlow {
            0% { box-shadow: 0 0 0 0 var(--glow-color); transform: scale(1); }
            50% { box-shadow: 0 0 20px 8px var(--glow-color); transform: scale(1.15); }
            100% { box-shadow: 0 0 0 0 var(--glow-color); transform: scale(1); }
        }

        .heartbeat-active {
            animation: heartbeatGlow 1.2s ease-in-out;
        }

        .nav-btn:hover {
            background: var(--nav-accent);
            color: white;
            border-color: var(--nav-accent);
        }

        /* Staggered transition delays */
        .nav-group.active .nav-btn:nth-child(1) { transition-delay: 0.1s; }
        .nav-group.active .nav-btn:nth-child(2) { transition-delay: 0.2s; }
        .nav-group.active .nav-btn:nth-child(3) { transition-delay: 0.3s; }

        svg { width: 20px; height: 20px; fill: none; stroke: currentColor; stroke-width: 2.5; stroke-linecap: round; stroke-linejoin: round; }
    </style>
</head>
<body>

    <div class="nav-dock">
        <button id="nav-launcher" onclick="toggleNav()">
            <svg viewBox="0 0 24 24"><polyline points="15 18 9 12 15 6"></polyline></svg>
        </button>

        <div class="nav-group" id="navGroup">
            <button class="nav-btn" onclick="window.scrollTo({top: 0, behavior: 'smooth'})" title="Top">
                <svg viewBox="0 0 24 24"><polyline points="18 15 12 9 6 15"></polyline></svg>
            </button>

            <a href="https://debeatzgh1.github.io/me-/" class="nav-btn" title="Home">
                <svg viewBox="0 0 24 24"><path d="M3 9l9-7 9 7v11a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2z"></path><polyline points="9 22 9 12 15 12 15 22"></polyline></svg>
            </a>

            <button class="nav-btn" onclick="window.scrollTo({top: document.body.scrollHeight, behavior: 'smooth'})" title="Bottom">
                <svg viewBox="0 0 24 24"><polyline points="6 9 12 15 18 9"></polyline></svg>
            </button>
        </div>
    </div>

    <script>
        function toggleNav() {
            const group = document.getElementById('navGroup');
            const launcher = document.getElementById('nav-launcher');
            const buttons = document.querySelectorAll('.nav-btn');
            
            const isOpening = !group.classList.contains('active');
            
            group.classList.toggle('active');
            launcher.classList.toggle('open');

            if (isOpening) {
                buttons.forEach((btn, index) => {
                    // Reset animation
                    btn.classList.remove('heartbeat-active');
                    void btn.offsetWidth; // Force reflow
                    
                    // Trigger staggered heartbeat
                    setTimeout(() => {
                        btn.classList.add('heartbeat-active');
                    }, (index + 1) * 200);
                });
            }
        }
    </script>

</body>
</html>



<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Multi-Tab Launcher</title>

<script src="https://cdn.tailwindcss.com"></script>

<style>
.modal-bg{
  display:none;
  position:fixed;
  inset:0;
  background:rgba(0,0,0,.75);
  backdrop-filter:blur(6px);
  z-index:9999;
}
.modal-box{
  width:100%;
  height:100%;
  background:#fff;
  display:flex;
  flex-direction:column;
}
.tabs{
  display:flex;
  gap:6px;
  padding:10px;
  background:#0f172a;
}
.tab{
  padding:8px 14px;
  border-radius:10px;
  font-size:13px;
  font-weight:700;
  color:#cbd5f5;
  cursor:pointer;
}
.tab.active{
  background:#2563eb;
  color:#fff;
}
.controls{
  display:flex;
  gap:8px;
  padding:8px 10px;
  background:#020617;
}
.ctrl-btn{
  background:rgba(255,255,255,.15);
  color:#fff;
  padding:6px 12px;
  border-radius:8px;
  font-size:12px;
  font-weight:700;
  cursor:pointer;
}
iframe{
  flex:1;
  width:100%;
  border:none;
}
.mobile-tabs{display:none}
@media (max-width:768px){
  .tabs{display:none}
  .mobile-tabs{
    display:flex;
    justify-content:space-around;
    background:#020617;
    padding:6px 0;
  }
  .mobile-tab{
    color:#cbd5f5;
    font-size:12px;
    font-weight:700;
    padding:6px 8px;
  }
  .mobile-tab.active{
    color:#fff;
    background:#2563eb;
    border-radius:8px;
  }
}
</style>
</head>

<body class="bg-gray-100">

<header class="text-center py-12">
  <h1 class="text-3xl font-bold">AI Hub</h1>
  <p class="text-gray-600 mt-2">All your platforms in one smart workspace</p>
  <button onclick="openLauncher('wordpress')" class="mt-6 bg-blue-600 text-white px-8 py-3 rounded-xl font-bold">
    Launch Hub
  </button>
</header>

<div class="modal-bg" id="modal">
  <div class="modal-box" id="modalBox">

    <div class="tabs">
      <div class="tab active" data-tab="wordpress" onclick="switchTab('wordpress')">Web</div>
      <div class="tab" data-tab="blogger" onclick="switchTab('blogger')">Home</div>
      <div class="tab" data-tab="slides" onclick="switchTab('slides')">Offers</div>
      <div class="tab" data-tab="sign" onclick="switchTab('sign')">Sign</div>
      <div class="tab" data-tab="about" onclick="switchTab('about')">Suggest</div>
    </div>

    <div class="controls">
      <div class="ctrl-btn" onclick="goBack()">⟵</div>
      <div class="ctrl-btn" onclick="goForward()">⟶</div>
      <div class="ctrl-btn" onclick="toggleFS()">⛶</div>
      <div class="ctrl-btn" onclick="closeLauncher()">✕</div>
    </div>

    <iframe id="frame"></iframe>

    <div class="mobile-tabs">
      <div class="mobile-tab active" data-tab="wordpress" onclick="switchTab('wordpress')">Web</div>
      <div class="mobile-tab" data-tab="blogger" onclick="switchTab('blogger')">Tools</div>
      <div class="mobile-tab" data-tab="slides" onclick="switchTab('slides')">Offers</div>
      <div class="mobile-tab" data-tab="sign" onclick="switchTab('sign')">Sign</div>
      <div class="mobile-tab" data-tab="about" onclick="switchTab('about')">Suggest</div>
    </div>

  </div>
</div>

<script>
const modal = document.getElementById("modal");
const frame = document.getElementById("frame");
const tabs = document.querySelectorAll(".tab");
const mobileTabs = document.querySelectorAll(".mobile-tab");

/* ✅ URL MAP (FIXED KEYS – SAME URLs) */
const URLS = {
  wordpress: "https://msha.ke/debeatzgh/",
  blogger: "https://debeatzgh1.github.io/debeatzgh/",
  slides: "https://mailchi.mp/3ab79c366503/iexz1xj8v3",
  sign: "https://mailchi.mp/0a569aa1173e/ai-decoder",
  about: "https://form.svhrt.com/60f4a0aeedc1993c8c7b3989"
};

let historyStack = [];
let historyIndex = -1;

function load(url){
  frame.src = url;
  if(historyStack[historyIndex] !== url){
    historyStack = historyStack.slice(0, historyIndex + 1);
    historyStack.push(url);
    historyIndex++;
  }
}

function openLauncher(tab){
  modal.style.display="flex";
  switchTab(tab);
}

function closeLauncher(){
  modal.style.display="none";
  frame.src="";
  historyStack=[];
  historyIndex=-1;
  if(document.fullscreenElement) document.exitFullscreen();
}

function switchTab(tab){
  tabs.forEach(t=>t.classList.remove("active"));
  mobileTabs.forEach(t=>t.classList.remove("active"));
  document.querySelectorAll(`[data-tab="${tab}"]`).forEach(t=>t.classList.add("active"));
  load(URLS[tab]);
}

function goBack(){
  if(historyIndex>0){
    historyIndex--;
    frame.src = historyStack[historyIndex];
  }
}
function goForward(){
  if(historyIndex<historyStack.length-1){
    historyIndex++;
    frame.src = historyStack[historyIndex];
  }
}

function toggleFS(){
  const el=document.getElementById("modalBox");
  if(!document.fullscreenElement) el.requestFullscreen();
  else document.exitFullscreen();
}
</script>

</body>
</html>
<!-- Elfsight AI Chatbot | Assistant Bot -->
<script src="https://elfsightcdn.com/platform.js" async></script>
<div class="elfsight-app-2552d2e4-68c0-45de-b815-0f6717b1a0e6" data-elfsight-app-lazy></div>
