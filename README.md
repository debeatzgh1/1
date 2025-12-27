                                         <!DOCTYPE html>
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
.carousel{
  position:relative;
  overflow:hidden;
}
.carousel-track{
  display:flex;
  transition:transform 0.6s ease;
}
.slide{
  min-width:100%;
  padding:20px;
}
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
#closeBtn{
  position:absolute;
  top:15px;
  left:15px;
  background:#ef4444;
  color:white;
  padding:10px 14px;
  border-radius:50%;
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

        <div class="slide">
          <div class="card">
            <h3>Work Smarter with AI</h3>
            <p>Boost productivity using AI-powered workflows.</p>
            <button class="btn" onclick="openDoc('https://docs.google.com/document/d/1D9_b4p374Av6KmnJu7WJ_-OdfUglaiNc/preview')">View</button>
          </div>
        </div>

        <div class="slide">
          <div class="card">
            <h3>Build a Tech Business</h3>
            <p>Everything needed to start a tech company.</p>
            <button class="btn" onclick="openDoc('https://docs.google.com/document/d/1_vtKBb2IFPjPoGPlzSfbYdOPQKocy5kg/preview')">View</button>
          </div>
        </div>

        <div class="slide">
          <div class="card">
            <h3>Online Store Setup</h3>
            <p>No skills required to start selling online.</p>
            <button class="btn" onclick="openDoc('https://docs.google.com/document/d/1zwmOqkbaUtWm-o-Sgr6Wqmto5Irlmnsr/preview')">View</button>
          </div>
        </div>

        <div class="slide">
          <div class="card">
            <h3>Side Hustle from Scratch</h3>
            <p>Turn ideas into income streams.</p>
            <button class="btn" onclick="openDoc('https://docs.google.com/document/d/1nkIOxY4vhtCtZT2eJJHFqlGUypMUWTkB/preview')">View</button>
          </div>
        </div>

      </div>

      <button class="nav prev" onclick="prevSlide()">‹</button>
      <button class="nav next" onclick="nextSlide()">›</button>
    </div>
  </div>

</div>

<!-- IFRAME VIEWER -->
<div id="viewer">
  <div id="closeBtn" onclick="closeDoc()">✕</div>
  <iframe id="docFrame"></iframe>
</div>

<!-- FLOATING SUPPORT -->
<div class="floating" onclick="openDoc('https://tally.so/r/3lWJZV')">
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

/* AUTO OPEN ON PAGE LOAD */
window.onload = function(){
  setTimeout(()=>{
    openDoc('https://docs.google.com/document/d/1D9_b4p374Av6KmnJu7WJ_-OdfUglaiNc/preview');
  },1500);
}

/* CAROUSEL */
let index=0;
const track=document.getElementById('track');
const slides=document.querySelectorAll('.slide');

function updateSlide(){
  track.style.transform=`translateX(-${index*100}%)`;
}
function nextSlide(){
  index=(index+1)%slides.length;
  updateSlide();
}
function prevSlide(){
  index=(index-1+slides.length)%slides.length;
  updateSlide();
}

/* AUTO SLIDE */
setInterval(nextSlide,5000);
</script>

</body>
</html>
                                                                                                                                                                | Project                                                                                                                                                      | Description                                                                                                         | Action                                                                                                           |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------- |
| ![Custom Blogger Theme](https://debeatzgh.wordpress.com/wp-content/uploads/2025/08/generateamobile-firstresponsivebloggertemplatewithcustomizablecolorsfontsandsections1576324612066211977.jpg)                                                            | **[Custom Blogger Theme with Dynamic Post Loading and Logo](https://debeatzgh1.github.io/Custom-Blogger-Theme-for-with-Dynamic-Post-Loading-and-Logo-/)**    | A responsive, mobile-first Blogger theme with customizable sections, dynamic post loading, and custom logo support. | [🔗 View Demo](https://debeatzgh1.github.io/Custom-Blogger-Theme-for-with-Dynamic-Post-Loading-and-Logo-/)       |
| ![Popup Generator](https://debeatzgh.wordpress.com/wp-content/uploads/2025/08/createatoolthatgeneratesiframeorcard-styleembedsforindividualbloggerpostscompletewiththumbnailtitleandreadmorebuttonforcross-blogpromotion754077096311972631.jpg)            | **[Popup HTML Page Generator](https://debeatzgh1.github.io/popup-html-page-generator-blogger/)**                                                             | Easily generate iframe or card-style embeds for individual Blogger posts with thumbnails and read-more buttons.     | [🔗 View Demo](https://debeatzgh1.github.io/popup-html-page-generator-blogger/)                                  |
| ![Newsletter Widget](https://debeatzgh.wordpress.com/wp-content/uploads/2025/08/amodernflat-styleillustrationofanotificationbellwithglowinghighlightssurroundedbyabstractshapespaperenvelopesanddigitalicons28emailmessageupdate293314991682681990671.jpg) | **[Sliding Newsletter Signup Widget](https://debeatzgh1.github.io/Sliding-Newsletter-Signup-Widget-with-Pulse-Animation/)**                                  | A modern newsletter signup widget with sliding animation and pulsing notification highlights.                       | [🔗 View Demo](https://debeatzgh1.github.io/Sliding-Newsletter-Signup-Widget-with-Pulse-Animation/)              |
| ![Product Carousel](https://debeatzgh.wordpress.com/wp-content/uploads/2025/08/designacleanmodernthumbnailforabloggerproductscarouseltool1711994558720457535.jpg)                                                                                          | **[Blogger Product Carousel with WhatsApp Floating Button](https://debeatzgh1.github.io/Blogger-Product-Carousel-with-WhatsApp-Floating-Button/)**           | Showcase Blogger products in a responsive carousel with a built-in WhatsApp floating button for instant contact.    | [🔗 View Demo](https://debeatzgh1.github.io/Blogger-Product-Carousel-with-WhatsApp-Floating-Button/)             |
| ![Floating Dock](https://debeatzgh.wordpress.com/wp-content/uploads/2025/08/amodernminimallayoutwithafloatingdockofcolorfulroundicons28patreonbloggergithub29ontherightsideofacleanwebpagemockup6676994054500999142.jpg)                                   | **[Floating Dock Smart Iframe Modal](https://debeatzgh1.github.io/-Floating-Dock-Smart-Iframe-Modal/)**                                                      | A modern floating dock with colorful round icons and iframe modal integration.                                      | [🔗 View Demo](https://debeatzgh1.github.io/-Floating-Dock-Smart-Iframe-Modal/)                                  |
| ![Tailwind Homepage](https://debeatzgh.wordpress.com/wp-content/uploads/2025/08/createamodernandcleanthumbnailforawebdevelopmentproducttitledmodernhomepagestylingtemplatewithtailwindcss3420170625469385526.jpg)                                          | **[Modern Homepage Styling with TailwindCSS](https://debeatzgh1.github.io/Modern-homepage-styling-with-TailwindCSS-/)**                                      | A clean and modern homepage layout template styled with TailwindCSS.                                                | [🔗 View Demo](https://debeatzgh1.github.io/Modern-homepage-styling-with-TailwindCSS-/)                          |
| ![TechAdapt Solutions](https://debeatzgh.wordpress.com/wp-content/uploads/2025/08/wp-17550417188267308669484942620808.jpg)                                                                                                                                 | **[TechAdapt Solutions – Strategies for Modern Startups](https://debeatzgh1.github.io/TechAdapt-Solutions-Strategies-for-Modern-Startups-and-Individuals/)** | Practical strategies, resources, and tools for startups and individuals adapting to the modern digital world.       | [🔗 View Demo](https://debeatzgh1.github.io/TechAdapt-Solutions-Strategies-for-Modern-Startups-and-Individuals/) |

---

## 🛠️ Features

* ✅ Fully responsive designs
* ✅ Blogger-friendly & easy to embed
* ✅ Lightweight, no heavy dependencies
* ✅ Includes floating buttons, modals, and animations
* ✅ Perfect for enhancing engagement & monetization

---

## 📌 Explore More Scripts

👉 Check out the full curated collection here:
[**Firebase Curated Front-End Components**](https://github.com/debeatzgh1/firebase-front-end-components)

---

## 💡 Contribution

Want to suggest improvements or add your own scripts?

* Open an **issue**
* Submit a **pull request**
* Share your ideas in the discussions

---

## 📜 License

This project is released under the **MIT License** – free to use, modify, and share with attribution.

---

✨ Designed for creators, bloggers, and developers who want to level up their Blogger sites with modern UI components.

---


# 🌐 Personal Portfolio Website

A simple and responsive personal portfolio website built with **HTML, CSS, and JavaScript**.  
This project is perfect for showcasing your skills, projects, and contact information.  

Live Demo 👉 [View Portfolio](https://debeatzgh.github.io/portfolio-site/)

---

## ✨ Features
- Responsive design (works on mobile & desktop)  
- Navigation bar with smooth scrolling  
- Hero section with intro & call-to-action button  
- About section with bio details  
- Projects section with cards  
- Contact section with email & social links  
- **Dark mode toggle** 🌙☀️  

---

## 🛠️ Technologies Used
- **HTML5** – Structure  
- **CSS3** – Styling & Responsive design  
- **JavaScript (Vanilla)** – Interactivity (dark mode toggle)  
- **GitHub Pages** – Free hosting & deployment  

---

## 🚀 Getting Started
To run this project locally:  

1. Clone the repository:
   ```bash
   git clone https://github.com/debeatzgh1/portfolio-site.git

# 🚀 DeBeatzGH – AI Tools & Side Hustle Hub  

![DeBeatzGH Thumbnail](https://debeatzgh.wordpress.com/wp-content/uploads/2025/08/designamodernminimalisticdesignfeaturinganai-themedicon28likeabraincircuitorrobot29overlaidwithdebeatzghoraitoolshustles6089986211026037047.jpg)  

## 🌟 About  
Welcome to **[DeBeatzGH](https://debeatzgh.wordpress.com/)** — your go-to hub for **AI tools, side hustle strategies, blogging resources, and digital growth guides**.  

Our platform is built to help **students, creators, startups, and professionals** unlock the power of AI, monetize their skills, and thrive in today’s digital economy.  

### ✨ What You’ll Find  
- 💡 Explore **AI prompts, tools, and hacks**  
- 📈 Discover **side hustle strategies & online income ideas**  
- ✍️ Access **blogging & digital business guides**  
- 🚀 Stay ahead with **regular updates and fresh insights**  

---

## 👉 Get Started  
🔥 **Start your journey today → [Visit DeBeatzGH]([https://debeatzgh.wordpress.com/](https://www.patreon.com/debeatzgh/collections))**  

---


<!-- README: DebeatzGH Digital Store (HTML-friendly for GitHub) -->
<div align="center">
  <a href="https://www.socialcreator.com/debeatzgh" target="_blank" rel="noopener">
    <img
      src="https://debeatzgh.wordpress.com/wp-content/uploads/2025/08/designadigitalproductse-commerceonlinedeals3545265155247625100.jpg"
      alt="DebeatzGH Digital Store"
      style="max-width:100%; border-radius:16px;"
    />
  </a>

  <h1 style="margin-top: 14px;">DebeatzGH Digital Store</h1>
  <p style="max-width:780px;">
    Your hub for AI insights, tech tutorials, side-hustle playbooks, and productivity tools.
    Learn, build, and launch digital projects faster.
  </p>

  <!-- CTAs -->
  <p>
    <a href="https://www.socialcreator.com/debeatzgh" target="_blank" rel="noopener"
       style="display:inline-block; padding:10px 16px; margin:4px; border-radius:999px; text-decoration:none; font-weight:600; border:1px solid #2563eb;">
      🚀 View Live App
    </a>
    <a href="https://github.com/debeatzgh1/Personal-Portfolio-site-" target="_blank" rel="noopener"
       style="display:inline-block; padding:10px 16px; margin:4px; border-radius:999px; text-decoration:none; font-weight:600; border:1px solid #111827;">
      ⭐ Star this Repo
    </a>
  </p>
</div>

<hr/>

<h2>Overview</h2>
<p>
  <strong>DebeatzGH</strong> helps beginners and creators build profitable digital assets:
  blogs, affiliate funnels, AI-assisted content, and more. Explore tutorials, tools, and
  ready-to-use components to speed up your workflow.
</p>

<h2>Features</h2>
<ul>
  <li><strong>AI & Tech Learning:</strong> Bite-sized guides for modern tools and workflows.</li>
  <li><strong>Side-Hustle Playbooks:</strong> Practical steps to validate and launch ideas.</li>
  <li><strong>Productivity Toolkit:</strong> Reusable widgets, templates, and scripts.</li>
  <li><strong>Beginner-Friendly:</strong> Clear explanations, curated resources, and examples.</li>
</ul>

<h2>Quick Start</h2>
<ol>
  <li>Clone:
    <pre><code>git clone https://github.com/debeatzgh1/Personal-Portfolio-site-</code></pre>
  </li>
  <li>Enter folder:
    <pre><code>cd debeatzgh</code></pre>
  </li>
  <li>Install deps (adjust to your stack):
    <pre><code># Node
npm install
npm run dev

# or Python
pip install -r requirements.txt
python app.py</code></pre>
  </li>
  <li>Open in browser:
    <pre><code>http://localhost:3000</code></pre>
  </li>
</ol>

<h2>Project Links</h2>
<ul>
  <li>🌐 Live App: <a href="https://www.socialcreator.com/debeatzgh" target="_blank" rel="noopener">socialcreator.com/debeatzgh</a></li>
  <li>🖼️ Thumbnail: <a href="https://debeatzgh.wordpress.com/wp-content/uploads/2025/08/designadigitalproductse-commerceonlinedeals3545265155247625100.jpg" target="_blank" rel="noopener">View image</a></li>
</ul>

<h2>Contributing</h2>
<p>
  Contributions are welcome! Open an issue for bugs or ideas. For changes, fork the repo,
  create a feature branch, and submit a pull request.
</p>

<h2>License</h2>
<p>
  Released under the <a href="./LICENSE">MIT License</a>.
</p>

<hr/>

<div align="center">
  <p><em>If this project helps you, consider giving it a star. It really helps! ⭐</em></p>
  <p>
    <a href="https://www.socialcreator.com/debeatzgh/?s=314768" target="_blank" rel="noopener"
       style="display:inline-block; padding:10px 16px; margin-top:6px; border-radius:10px; text-decoration:none; font-weight:600; border:1px solid #2563eb;">
      PRODUCTS →
    </a>
  </p>
</div>
