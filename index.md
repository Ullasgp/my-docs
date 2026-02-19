<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Documentation Hub</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: "Segoe UI", Arial, sans-serif;
  }

  body {
    display: flex;
    flex-direction: column;
    min-height: 100vh;
    background: #f7f9fc;
  }

  /* ===== Header ===== */
  header {
    background: #0d47a1;
    color: white;
    padding: 16px 24px;
    font-size: 22px;
    font-weight: 600;
    box-shadow: 0 2px 6px rgba(0,0,0,0.1);
  }

  /* ===== Layout ===== */
  .container {
    display: flex;
    flex: 1;
  }

  /* ===== Sidebar ===== */
  nav {
    width: 260px;
    background: white;
    border-right: 1px solid #e0e0e0;
    padding: 20px;
    position: sticky;
    top: 0;
    height: calc(100vh - 64px);
    overflow-y: auto;
  }

  nav h3 {
    margin-bottom: 15px;
    color: #0d47a1;
  }

  nav a {
    display: block;
    padding: 10px 12px;
    margin-bottom: 6px;
    color: #333;
    text-decoration: none;
    border-radius: 6px;
    transition: 0.2s;
    font-size: 14px;
  }

  nav a:hover {
    background: #e3f2fd;
    color: #0d47a1;
  }

  nav a.active {
    background: #0d47a1;
    color: white;
    font-weight: 500;
  }

  /* ===== Content ===== */
  main {
    flex: 1;
    padding: 40px;
    background: #f7f9fc;
  }

  section {
    background: white;
    padding: 28px;
    border-radius: 10px;
    margin-bottom: 40px;
    box-shadow: 0 2px 8px rgba(0,0,0,0.05);
  }

  section h2 {
    color: #0d47a1;
    margin-bottom: 12px;
  }

  section h3 {
    margin-top: 18px;
    margin-bottom: 8px;
    color: #333;
  }

  ul {
    margin-left: 20px;
    margin-top: 8px;
  }

  /* ===== Footer ===== */
  footer {
    background: #263238;
    color: white;
    text-align: center;
    padding: 14px;
    font-size: 14px;
  }

  html {
    scroll-behavior: smooth;
  }

  /* ===== Mobile ===== */
  @media (max-width: 768px) {
    nav {
      width: 200px;
    }
    main {
      padding: 20px;
    }
  }
</style>
</head>

<body>

<header>
  📘 Enterprise Documentation Hub
</header>

<div class="container">

  <!-- ===== Sidebar ===== -->
  <nav>
    <h3>Contents</h3>

    <a href="#intro">Introduction</a>
    <a href="#jenkins">Jenkins Pipeline</a>
    <a href="#more">Add More Topics</a>
  </nav>

  <!-- ===== Main Content ===== -->
  <main>

    <!-- ===== Intro ===== -->
    <section id="intro">
      <h2>Introduction</h2>
      <p>
        Welcome to the enterprise documentation portal. Use the navigation
        menu to explore different technical topics and implementation guides.
      </p>
    </section>

    <!-- ===== Jenkins Topic ===== -->
    <section id="jenkins">
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
      <p>
        This Jenkins <strong>Declarative CI pipeline</strong> standardizes the build
        and integration process for Java-based microservices.
      </p>

      <p>It automates:</p>
      <ul>
        <li>Source code checkout</li>
        <li>Build and unit testing</li>
        <li>Code quality and security scans</li>
        <li>Artifact publishing (JAR and Docker images)</li>
        <li>Triggering downstream CD pipelines</li>
      </ul>

      <p>
        The pipeline is designed to be <strong>centrally governed</strong> by the
        Middleware / DevOps team and consumed by implementation teams with minimal configuration.
      </p>

      <h3>Who Should Read This?</h3>
      <ul>
        <li><strong>Implementation Teams</strong> – to onboard and use the pipeline</li>
        <li><strong>Middleware / DevOps Team</strong> – to configure and maintain CI Jenkins</li>
        <li><strong>Managers / Leads</strong> – to understand responsibilities and flow</li>
      </ul>

      <h3>Ownership & Responsibilities</h3>
      <h3>Middleware / DevOps Team (Jenkins Owners)</h3>

      <p>Responsible for central and one-time setup:</p>
      <ul>
        <li>Jenkins server and agent configuration</li>
        <li>Jenkins plugin installation</li>
        <li>Jenkins global tools (Java, Maven, NodeJS)</li>
        <li>Docker installation on Jenkins agents</li>
        <li>SonarQube server integration and webhook configuration</li>
        <li>Artifactory (JFrog) access</li>
        <li>Jenkins credentials creation and maintenance</li>
        <li>Dependency-Track server setup (if enabled)</li>
        <li>Creation of CI and downstream CD Jenkins jobs</li>
      </ul>
    </section>

    <!-- ===== Placeholder for future topics ===== -->
    <section id="more">
      <h2>Add More Topics</h2>
      <p>
        You can easily add more documentation sections by copying a section block
        and updating the sidebar navigation.
      </p>
    </section>

  </main>
</div>

<footer>
  © 2026 Enterprise Docs | Built for DevOps & Implementation Teams
</footer>

<script>
  // ===== Active menu highlight =====
  const sections = document.querySelectorAll("section");
  const navLinks = document.querySelectorAll("nav a");

  window.addEventListener("scroll", () => {
    let current = "";

    sections.forEach(section => {
      const sectionTop = section.offsetTop - 120;
      if (pageYOffset >= sectionTop) {
        current = section.getAttribute("id");
      }
    });

    navLinks.forEach(a => {
      a.classList.remove("active");
      if (a.getAttribute("href") === "#" + current) {
        a.classList.add("active");
      }
    });
  });
</script>

</body>
</html>
