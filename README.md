
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sleek Floating Banner</title>
    <style>
        /* Modern CSS reset for consistency */
        *, *::before, *::after {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: 'Segoe UI', Roboto, Helvetica, Arial, sans-serif;
            min-height: 200vh; /* Adds scrollable height to visualize the fixed positioning */
            background-color: #121212; /* A dark, neutral background */
            color: #fff;
        }

        /* MAIN FLOATING BANNER CONTAINER
           Fixed to the top center of the screen
        */
        #sleek-floating-banner {
            position: fixed;
            top: 20px; /* Slight offset from the top border */
            left: 50%;
            transform: translateX(-50%); /* Centers horizontally */
            width: 340px; /* Compact, friendly width for desktop/mobile */
            height: 52px;
            background: rgba(30, 30, 30, 0.9); /* Dark semi-transparent background */
            backdrop-filter: blur(10px); /* Modern 'glassmorphism' effect */
            -webkit-backdrop-filter: blur(10px); /* Safari support */
            border: 1px solid rgba(255, 255, 255, 0.1); /* Subtle outline */
            border-radius: 50px; /* Fully rounded edges for a sleek pill look */
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5); /* Strong shadow for depth */
            display: flex;
            align-items: center;
            justify-content: space-between; /* Icon+Text on left, button on right */
            padding: 0 6px 0 16px; /* Optimized padding for the components */
            z-index: 10000; /* Ensures it stays above all other content */
            overflow: hidden; /* Needed for the marquee slide effect */
            
            /* Entry animation */
            animation: bannerEntry 0.6s cubic-bezier(0.175, 0.885, 0.32, 1.275) forwards;
            opacity: 0;
            transition: all 0.3s ease;
        }

        /* Hover effect to highlight the interactive nature */
        #sleek-floating-banner:hover {
            transform: translateX(-50%) scale(1.03);
            border-color: #FF1493; /* DeepPink border highlight on hover */
        }

        /* Banner entry animation (slides in and bounces slightly) */
        @keyframes bannerEntry {
            from { top: -60px; opacity: 0; }
            to { top: 20px; opacity: 1; }
        }

        /* --- MARQUEE SLIDER STYLES --- */
        .banner-text-slider {
            flex: 1;
            height: 22px; /* Set height to constrain the text */
            overflow: hidden; /* Masks text outside the area */
            position: relative;
            margin-right: 12px;
        }

        .slide-inner {
            display: flex;
            flex-direction: column; /* Stacks text vertically for sliding */
            animation: verticalSlide 8s cubic-bezier(0.645, 0.045, 0.355, 1) infinite;
        }

        /* Text element properties */
        .slide-inner span {
            height: 22px; /* Matches parent height */
            color: rgba(255, 255, 255, 0.9); /* Slightly off-white for better readability */
            font-size: 0.8rem;
            font-weight: 600; /* Semi-bold */
            display: flex;
            align-items: center;
            gap: 8px; /* Gap for the indicator dot */
            white-space: nowrap; /* Prevents text wrapping */
        }

        /* Color highlight for key inscriptions */
        .highlight-text {
            color: #FF1493; /* DeepPink */
        }

        /* Subtle animated dot for live status feel */
        .live-dot {
            width: 7px;
            height: 7px;
            background-color: #FF1493;
            border-radius: 50%;
            box-shadow: 0 0 10px rgba(255, 20, 147, 0.8);
            animation: pulseDot 1.5s infinite;
        }

        /* Pulse animation for the live dot */
        @keyframes pulseDot {
            0%, 100% { opacity: 1; transform: scale(1); }
            50% { opacity: 0.3; transform: scale(1.2); }
        }

        /* Vertical Slide Keyframes:
           4 states (3 texts + return to 1). 
           Uses percentages to control pause duration at each state.
        */
        @keyframes verticalSlide {
            0%, 22% { transform: translateY(0); } /* Pauses on Text 1 */
            33%, 55% { transform: translateY(-22px); } /* Slides to and Pauses on Text 2 */
            66%, 88% { transform: translateY(-44px); } /* Slides to and Pauses on Text 3 */
            100% { transform: translateY(0); } /* Loops back to Text 1 smoothly */
        }

        /* --- BUTTON STYLES --- */
        .launch-btn {
            background-color: #FF1493; /* Vibrant DeepPink for main color */
            color: #fff;
            padding: 9px 20px;
            border-radius: 25px; /* Rounded pill style to match banner */
            font-size: 0.75rem;
            font-weight: 900; /* Extra bold text for contrast */
            border: none;
            cursor: pointer;
            text-transform: uppercase;
            letter-spacing: 1px;
            text-decoration: none; /* Removes underline for <a> tags */
            display: flex;
            align-items: center;
            gap: 6px;
            transition: all 0.3s ease;
            box-shadow: 0 4px 15px rgba(255, 20, 147, 0.3); /* Soft DeepPink glow */
        }

        /* Button interaction effects */
        .launch-btn:hover {
            background-color: #ff50ac; /* Lighter DeepPink on hover */
            transform: translateY(-1px);
            box-shadow: 0 6px 20px rgba(255, 20, 147, 0.5); /* Stronger DeepPink glow */
        }

        .launch-btn:active {
            transform: translateY(1px) scale(0.98); /* Click interaction feedback */
        }

        /* --- SVG ICON STYLE --- */
        .arrow-icon {
            width: 13px;
            height: 13px;
            fill: none;
            stroke: currentColor; /* Matches text color (#fff) */
            stroke-width: 3;
            transition: transform 0.3s ease;
        }

        /* Hover animation specifically for the icon */
        .launch-btn:hover .arrow-icon {
            transform: translateX(3px); /* Arrow nudges right on hover */
        }
    </style>
</head>
<body>

    <div id="sleek-floating-banner" onclick="openHomeLink()">
        <div class="banner-text-slider">
            <div class="slide-inner">
                <span>
                    <div class="live-dot"></div> 
                    DeBeatz<span class="highlight-text">GH</span> Resource Hub
                </span>
                <span>
                    <div class="live-dot"></div>
                    Lifestyle <span class="highlight-text">&</span> Strategy
                </span>
                <span>
                    <div class="live-dot"></div>
                    Latest updates are <span class="highlight-text">Live</span>
                </span>
            </div>
        </div>

        <button class="launch-btn" onclick="openHomeLink(event)">
            OPEN 
            <svg class="arrow-icon" viewBox="0 0 24 24" aria-hidden="true">
                <path d="M5 12h14M12 5l7 7-7 7"/>
            </svg>
        </button>
    </div>

    <script>
        /**
         * Opens the specified URL in a new tab without navigating
         * away from the current page.
         * @param {Event} e - Optional event object to prevent bubbling.
         */
        function openHomeLink(e) {
            // Check if event exists and stop propagation so clicking the button
            // doesn't also trigger the banner's onclick.
            if (e && e.stopPropagation) {
                e.stopPropagation();
            }
            
            // window.open(url, '_blank') opens in a new tab.
            window.open("https://debeatzgh1.github.io/ai-chat/", "_blank");
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
  slides: "https://beatzde4.blogspot.com/p/advertise-online-for-free.html",
  sign: "https://beatzde4.blogspot.com/p/advertise-online-for-free.html",
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
