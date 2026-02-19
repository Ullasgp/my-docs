<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Enterprise Documentation Portal</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
*{margin:0;padding:0;box-sizing:border-box;font-family:"Segoe UI",Arial,sans-serif}

body{background:#f4f6fb;color:#222}

/* ===== Header ===== */
header{
  position:sticky;
  top:0;
  z-index:1000;
  background:#0b3d91;
  color:#fff;
  padding:14px 20px;
  display:flex;
  align-items:center;
  justify-content:space-between;
  box-shadow:0 2px 8px rgba(0,0,0,.15);
}

.header-left{display:flex;align-items:center;gap:12px;font-weight:600;font-size:20px}

.menu-btn{
  font-size:22px;
  cursor:pointer;
  display:none;
}

/* ===== Layout ===== */
.layout{display:flex;min-height:calc(100vh - 56px)}

/* ===== Sidebar ===== */
.sidebar{
  width:270px;
  background:#fff;
  border-right:1px solid #e0e0e0;
  padding:18px;
  overflow-y:auto;
  transition:.3s;
}

.sidebar h3{color:#0b3d91;margin-bottom:10px}

.search-box{
  width:100%;
  padding:8px;
  margin-bottom:15px;
  border:1px solid #ccc;
  border-radius:6px;
}

.nav-group{margin-bottom:12px}

.group-title{
  font-weight:600;
  padding:8px;
  cursor:pointer;
  background:#eef3ff;
  border-radius:6px;
  margin-bottom:6px;
}

.nav-links a{
  display:block;
  padding:7px 10px;
  text-decoration:none;
  color:#333;
  border-radius:5px;
  font-size:14px;
}

.nav-links a:hover{background:#e3f2fd;color:#0b3d91}
.nav-links a.active{background:#0b3d91;color:#fff}

/* ===== Content ===== */
.content{
  flex:1;
  padding:40px;
}

.section-card{
  background:#fff;
  padding:28px;
  border-radius:10px;
  margin-bottom:40px;
  box-shadow:0 2px 8px rgba(0,0,0,.06);
}

.section-card h2{color:#0b3d91;margin-bottom:10px}
.section-card h3{margin-top:18px;margin-bottom:6px}

ul{margin-left:20px;margin-top:6px}

/* ===== Footer ===== */
footer{
  text-align:center;
  padding:14px;
  background:#263238;
  color:#fff;
  font-size:14px;
}

/* ===== Mobile ===== */
@media(max-width:900px){
  .menu-btn{display:block}
  .sidebar{
    position:fixed;
    left:-280px;
    top:56px;
    height:calc(100vh - 56px);
    z-index:999;
  }
  .sidebar.show{left:0}
  .content{padding:22px}
}

html{scroll-behavior:smooth}
</style>
</head>

<body>

<header>
  <div class="header-left">
    <span class="menu-btn" onclick="toggleMenu()">☰</span>
    📘 Enterprise Docs Portal
  </div>
  <div>DevOps Knowledge Base</div>
</header>

<div class="layout">

  <!-- ===== Sidebar ===== -->
  <aside class="sidebar" id="sidebar">

    <input type="text" class="search-box" placeholder="Search topics..." onkeyup="filterMenu(this.value)">

    <div class="nav-group">
      <div class="group-title" onclick="toggleGroup(this)">Getting Started</div>
      <div class="nav-links">
        <a href="#intro">Introduction</a>
      </div>
    </div>

    <div class="nav-group">
      <div class="group-title" onclick="toggleGroup(this)">CI/CD Pipelines</div>
      <div class="nav-links">
        <a href="#jenkins">Jenkins Pipeline</a>
      </div>
    </div>

    <div class="nav-group">
      <div class="group-title" onclick="toggleGroup(this)">More Topics</div>
      <div class="nav-links">
        <a href="#more">Add More Topics</a>
      </div>
    </div>

  </aside>

  <!-- ===== Content ===== -->
  <main class="content">

    <section id="intro" class="section-card">
      <h2>Introduction</h2>
      <p>
        Welcome to the enterprise documentation portal designed for scalable
        DevOps and implementation teams.
      </p>
    </section>

    <section id="jenkins" class="section-card">
      <h2>Jenkins Pipeline for Microservice Build and Deployment</h2>

      <p>
        <img src="https://img.shields.io/badge/Jenkins-CI%2FCD-blue?logo=jenkins">
        <img src="https://img.shields.io/badge/Java-21-red?logo=openjdk">
        <img src="https://img.shields.io/badge/Maven-Build-blue?logo=apachemaven">
        <img src="https://img.shields.io/badge/TruffleHog-Success-brightgreen">
        <img src="https://img.shields.io/badge/Docker-Enabled-blue?logo=docker">
        <img src="https://img.shields.io/badge/SonarQube-Quality%20Gate-brightgreen?logo=sonarqube">
        <img src="https://img.shields.io/badge/Trivy-Security-critical?logo=aquasec">
        <img src="https://img.shields.io/badge/JFrog-Artifactory-green?logo=jfrog">
        <img src="https://img.shields.io/badge/GitLab-Source-orange?logo=gitlab">
      </p>

      <h3>Overview</h3>
      <p>This Jenkins Declarative CI pipeline standardizes Java microservice build and integration.</p>

      <ul>
        <li>Source code checkout</li>
        <li>Build and unit testing</li>
        <li>Quality and security scans</li>
        <li>Artifact publishing</li>
        <li>Trigger downstream CD</li>
      </ul>

      <h3>Ownership & Responsibilities</h3>
      <ul>
        <li>Jenkins server and agent configuration</li>
        <li>Plugin and global tools setup</li>
        <li>Docker installation on agents</li>
        <li>SonarQube integration</li>
        <li>JFrog access configuration</li>
      </ul>
    </section>

    <section id="more" class="section-card">
      <h2>Add More Topics</h2>
      <p>Extend the portal by adding new navigation items and sections.</p>
    </section>

  </main>
</div>

<footer>
  © 2026 Enterprise DevOps Docs
</footer>

<script>
function toggleMenu(){
  document.getElementById("sidebar").classList.toggle("show");
}

function toggleGroup(el){
  const links = el.nextElementSibling;
  links.style.display = links.style.display === "none" ? "block" : "none";
}

function filterMenu(val){
  val = val.toLowerCase();
  document.querySelectorAll(".nav-links a").forEach(a=>{
    a.style.display = a.textContent.toLowerCase().includes(val) ? "block":"none";
  });
}

/* active link */
const sections=document.querySelectorAll("section");
const navLinks=document.querySelectorAll(".nav-links a");

window.addEventListener("scroll",()=>{
  let current="";
  sections.forEach(sec=>{
    if(pageYOffset>=sec.offsetTop-120){current=sec.id;}
  });
  navLinks.forEach(a=>{
    a.classList.remove("active");
    if(a.getAttribute("href")==="#"+current){a.classList.add("active");}
  });
});
</script>

</body>
</html>
