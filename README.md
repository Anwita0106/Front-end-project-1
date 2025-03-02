<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>RocketAir Clone Demo</title>
  
  <!-- GSAP CDN (for animations) -->
  <script src="https://unpkg.com/gsap@3.12.2/dist/gsap.min.js"></script>

  <!-- Inline CSS -->
  <style>
    /* RESET & GLOBAL STYLES */
    * {
      margin: 0; 
      padding: 0; 
      box-sizing: border-box;
    }
    body {
      font-family: "Helvetica Neue", Arial, sans-serif;
      background-color: #000; 
      color: #fff;
      overflow-x: hidden;
    }
    a {
      text-decoration: none; 
      color: inherit;
    }

    /* NAVBAR */
    header {
      position: fixed;
      top: 0;
      width: 100%;
      background: rgba(0, 0, 0, 0.85);
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 20px 40px;
      z-index: 999;
    }
    .logo {
      font-size: 1.5rem;
      font-weight: bold;
      letter-spacing: 1px;
    }
    nav ul {
      list-style: none;
      display: flex;
      gap: 30px;
    }
    nav li {
      font-size: 1rem;
      font-weight: 500;
      text-transform: uppercase;
    }

    /* HERO SECTION */
    .hero {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: flex-start;
      padding: 0 40px;
      height: 100vh;
      background: url("https://via.placeholder.com/1600x900") no-repeat center/cover;
      margin-top: 80px; /* offset for fixed header */
      position: relative;
    }
    .hero-overlay {
      position: absolute;
      top: 0; 
      left: 0;
      width: 100%; 
      height: 100%;
      background: linear-gradient(to bottom right, rgba(0,0,0,0.7), rgba(0,0,0,0.3));
      z-index: 1;
    }
    .hero-content {
      position: relative;
      z-index: 2;
      max-width: 600px;
    }
    .hero h1 {
      font-size: 3rem;
      line-height: 1.2;
      margin-bottom: 20px;
      font-weight: 700;
    }
    .hero p {
      font-size: 1.1rem;
      margin-bottom: 30px;
      line-height: 1.6;
    }
    .cta-button {
      background: #ff5100;
      padding: 15px 25px;
      border: none;
      font-size: 1rem;
      cursor: pointer;
      transition: background 0.3s ease;
    }
    .cta-button:hover {
      background: #e64500;
    }

    /* FEATURED SECTION */
    .featured {
      background: #111;
      padding: 80px 40px;
      text-align: left;
    }
    .featured h2 {
      font-size: 2rem;
      margin-bottom: 40px;
      font-weight: 600;
    }
    .project-cards {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 20px;
    }
    .card {
      background: #222;
      padding: 20px;
      border-radius: 5px;
      transition: transform 0.3s ease, box-shadow 0.3s ease;
      cursor: pointer;
    }
    .card:hover {
      transform: translateY(-5px);
      box-shadow: 0 10px 20px rgba(0,0,0,0.5);
    }
    .card img {
      width: 100%;
      height: auto;
      border-radius: 3px;
      margin-bottom: 15px;
    }
    .card h3 {
      font-size: 1.2rem;
      margin-bottom: 10px;
      font-weight: 600;
    }
    .card p {
      font-size: 0.95rem;
      line-height: 1.5;
      opacity: 0.8;
    }

    /* FOOTER */
    footer {
      background: #000;
      text-align: center;
      padding: 40px;
    }
    footer p {
      font-size: 0.9rem;
      opacity: 0.7;
    }

    /* RESPONSIVE */
    @media (max-width: 768px) {
      .hero h1 {
        font-size: 2rem;
      }
      .hero p {
        font-size: 1rem;
      }
      header {
        padding: 15px 20px;
      }
      .nav-links {
        font-size: 0.9rem;
      }
    }
  </style>
</head>
<body>
  <!-- NAVBAR -->
  <header>
    <div class="logo">RocketAir</div>
    <nav>
      <ul>
        <li><a href="#hero">Home</a></li>
        <li><a href="#featured">Work</a></li>
        <li><a href="#about">About</a></li>
        <li><a href="#footer">Contact</a></li>
      </ul>
    </nav>
  </header>

  <!-- HERO SECTION -->
  <section class="hero" id="hero">
    <div class="hero-overlay"></div>
    <div class="hero-content">
      <h1>Designing Digital Experiences<br>That Shape the Future</h1>
      <p>
        We’re a design and technology studio creating impactful digital products and brands
        for forward-thinking companies.
      </p>
      <button class="cta-button" id="explore-btn">Explore Our Work</button>
    </div>
  </section>

  <!-- FEATURED PROJECTS -->
  <section class="featured" id="featured">
    <h2>Featured Projects</h2>
    <div class="project-cards">
      <div class="card">
        <img src="https://via.placeholder.com/400x250" alt="Project 1">
        <h3>Project One</h3>
        <p>Revolutionary web platform that redefines user engagement and brand identity.</p>
      </div>
      <div class="card">
        <img src="https://via.placeholder.com/400x250" alt="Project 2">
        <h3>Project Two</h3>
        <p>Modern e-commerce experience focusing on seamless shopping and bold design.</p>
      </div>
      <div class="card">
        <img src="https://via.placeholder.com/400x250" alt="Project 3">
        <h3>Project Three</h3>
        <p>Mobile app that transforms everyday tasks into delightful user experiences.</p>
      </div>
    </div>
  </section>

  <!-- ABOUT SECTION (Optional) -->
  <section class="featured" id="about">
    <h2>About RocketAir</h2>
    <p style="max-width: 700px; margin: 0 auto;">
      We’re a diverse team of strategists, designers, and developers who thrive on innovation.
      Our mission is to help companies discover their digital edge and connect with audiences
      in impactful ways.
    </p>
  </section>

  <!-- FOOTER -->
  <footer id="footer">
    <p>&copy; 2025 RocketAir Clone. All Rights Reserved.</p>
  </footer>

  <!-- Inline JavaScript -->
  <script>
    // Wait for DOM
    document.addEventListener("DOMContentLoaded", function() {
      // GSAP Animations
      gsap.from("header", { 
        duration: 1, 
        y: -80, 
        opacity: 0, 
        ease: "power2.out" 
      });
      gsap.from(".hero-content h1", {
        duration: 1.2,
        x: -50,
        opacity: 0,
        delay: 0.3,
        ease: "power2.out"
      });
      gsap.from(".hero-content p", {
        duration: 1,
        x: 50,
        opacity: 0,
        delay: 0.6,
        ease: "power2.out"
      });
      gsap.from(".cta-button", {
        duration: 1,
        scale: 0.8,
        opacity: 0,
        delay: 1,
        ease: "bounce.out"
      });
      
      // Animate featured section on scroll
      gsap.from(".featured h2", {
        scrollTrigger: ".featured", // requires ScrollTrigger plugin if you want advanced triggers
        duration: 1,
        y: 50,
        opacity: 0,
        ease: "power2.out"
      });
      // (If you want advanced scroll-based animations, you'd add the GSAP ScrollTrigger plugin.)

      // Button click
      const exploreBtn = document.getElementById("explore-btn");
      exploreBtn.addEventListener("click", function() {
        // Smooth scroll to Featured section
        document.getElementById("featured").scrollIntoView({ behavior: "smooth" });
      });
    });
  </script>
</body>
</html>
