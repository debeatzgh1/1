<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Debeatzgh Multi-Tab Launcher</title>

<script src="https://cdn.tailwindcss.com"></script>

<style>
/* ===== MODAL ===== */
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

/* ===== DESKTOP TABS ===== */
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

/* ===== CONTROLS ===== */
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

/* ===== IFRAME ===== */
iframe{
  flex:1;
  width:100%;
  border:none;
}

/* ===== MOBILE BOTTOM TABS ===== */
.mobile-tabs{
  display:none;
}
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
  <h1 class="text-3xl font-bold">Debeatzgh AI Hub</h1>
  <p class="text-gray-600 mt-2">All your platforms in one smart workspace</p>

  <button onclick="openLauncher('wordpress')" class="mt-6 bg-blue-600 text-white px-8 py-3 rounded-xl font-bold">
    Launch Hub
  </button>
</header>

<!-- MODAL -->
<div class="modal-bg" id="modal">
  <div class="modal-box" id="modalBox">

    <!-- DESKTOP TABS -->
    <div class="tabs">
      <div class="tab active" data-tab="wordpress" onclick="switchTab('wordpress')">WordPress</div>
      <div class="tab" data-tab="blogger" onclick="switchTab('blogger')">Blogger</div>
      <div class="tab" data-tab="slides" onclick="switchTab('slides')">Slides</div>
      <div class="tab" data-tab="sign" onclick="switchTab('sign')">Sign</div>
      <div class="tab" data-tab="about" onclick="switchTab('about')">About</div>
    </div>

    <!-- CONTROLS -->
    <div class="controls">
      <div class="ctrl-btn" onclick="goBack()">⟵</div>
      <div class="ctrl-btn" onclick="goForward()">⟶</div>
      <div class="ctrl-btn" onclick="toggleFS()">⛶</div>
      <div class="ctrl-btn" onclick="closeLauncher()">✕</div>
    </div>

    <!-- IFRAME -->
    <iframe id="frame"></iframe>

    <!-- MOBILE TABS -->
    <div class="mobile-tabs">
      <div class="mobile-tab active" data-tab="wordpress" onclick="switchTab('wordpress')">WP</div>
      <div class="mobile-tab" data-tab="blogger" onclick="switchTab('blogger')">Blog</div>
      <div class="mobile-tab" data-tab="slides" onclick="switchTab('slides')">Slides</div>
      <div class="mobile-tab" data-tab="sign" onclick="switchTab('sign')">Sign</div>
      <div class="mobile-tab" data-tab="about" onclick="switchTab('about')">About</div>
    </div>

  </div>
</div>

<script>
const modal = document.getElementById("modal");
const frame = document.getElementById("frame");
const tabs = document.querySelectorAll(".tab");
const mobileTabs = document.querySelectorAll(".mobile-tab");

/* ===== URL MAP ===== */
const URLS = {
  Web: "https://msha.ke/debeatzgh/",
  Home: "https://docs.google.com/document/d/1yTeRMaF8GEkTZf34EK7eOdxe6sCOCNxX/edit?usp=drivesdk&ouid=116845182021782803040&rtpof=true&sd=true",
  offers: "https://docs.google.com/presentation/d/1F7_mDSijSndGly1Q05YqOZHI1LaSjjt7/preview",
  sign: "https://docs.google.com/forms/d/e/1FAIpQLSdXCPUz1JBq0W8MHN9VOE0p6cnp5Wtr74Ox2gqLLyzKi0UwKA/viewform",
  suggest: "https://form.jotform.com/241335470278053"
};

/* ===== SAME FRAME RULES ===== */
const SAME_FRAME_DOMAINS = [
  "wordpress.com",
  "blogspot.com",
  "docs.google.com",
  "github.io",
  "jotform.com",
  "tally.so",
  "msha.ke"
];

/* ===== HISTORY ===== */
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

/* ===== OPEN / CLOSE ===== */
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

/* ===== SWITCH TAB ===== */
function switchTab(tab){
  tabs.forEach(t=>t.classList.remove("active"));
  mobileTabs.forEach(t=>t.classList.remove("active"));

  document.querySelectorAll(`[data-tab="${tab}"]`).forEach(t=>{
    t.classList.add("active");
  });

  load(URLS[tab]);
}

/* ===== NAVIGATION ===== */
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

/* ===== FULLSCREEN ===== */
function toggleFS(){
  const el=document.getElementById("modalBox");
  if(!document.fullscreenElement) el.requestFullscreen();
  else document.exitFullscreen();
}

/* ===== IFRAME LINK RULES ===== */
frame.addEventListener("load", ()=>{
  try{
    const doc = frame.contentDocument || frame.contentWindow.document;
    doc.querySelectorAll("a[href]").forEach(link=>{
      link.addEventListener("click", e=>{
        const href = link.href;
        if(!href) return;

        const sameFrame = SAME_FRAME_DOMAINS.some(d=>href.includes(d));

        if(sameFrame){
          e.preventDefault();
          load(href);
        }else{
          link.target="_blank";
          link.rel="noopener noreferrer";
        }
      });
    });
  }catch(err){
    console.warn("Cross-domain restriction applied");
  }
});
</script>

</body>
</html>
