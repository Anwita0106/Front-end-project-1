<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>RocketAir Clone</title>
  <!-- GSAP CDN -->
  <script src="https://unpkg.com/gsap@3.12.2/dist/gsap.min.js"></script>
  <style>
    /* Reset & General Styles */
    body {
      margin: 0;
      padding: 0;
      font-family: Arial, sans-serif;
      background: #111;
      color: #fff;
      text-align: center;
    }
    /* Header & Navbar */
    header {
      background: rgba(0, 0, 0, 0.8);
      padding: 15px 30px;
      position: fixed;
      top: 0;
      width: 100%;
      display: flex;
      justify-content: space-between;
      align-items: center;
      z-index: 1000;
    }
    .logo {
      font-size: 24px;
      font-weight: bold;
    }
    .nav-links {
      list-style: none;
      margin: 0;
      padding: 0;
      display: flex;
    }
    .nav-links li {
      margin: 0 15px;
    }
    .nav-links a {
      text-decoration: none;
      color: #fff;
      font-size: 18px;
    }
    /* Hero Section */
    .hero {
      margin-top: 70px; /* Offset for fixed header */
      height: 100vh;
      background: url('https://via.placeholder.com/1920x1080') no-repeat center center/cover;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      padding: 20px;
    }
    .hero h1 {
      font-size: 48px;
      margin: 0;
      opacity: 0;
    }
    .hero p {
      font-size: 20px;
      margin: 15px 0;
      opacity: 0;
    }
    .cta-btn {
      padding: 12px 25px;
      font-size: 18px;
      background: orangered;
      color: white;
      border: none;
      cursor: pointer;
      transition: background 0.3s;
    }
    .cta-btn:hover {
      background: red;
    }
    /* Dynamic Content Section */
    .dynamic-content {
      padding: 50px 20px;
      background: #222;
    }
    /* Footer */
    footer {
      background: rgba(0, 0, 0, 0.9);
      padding: 20px;
      position: fixed;
      bottom: 0;
      width: 100%;
      z-index: 1000;
    }
  </style>
</head>
<body>
  <!-- Header & Navbar -->
  <header>
    <div class="logo">RocketAir</div>
    <ul class="nav-links">
      <li><a href="#">Home</a></li>
      <li><a href="#">Services</a></li>
      <li><a href="#">Projects</a></li>
      <li><a href="#">Contact</a></li>
    </ul>
  </header>
  
  <!-- Hero Section -->
  <section class="hero">
    <h1>Welcome to RocketAir</h1>
    <p>Creative digital experiences that inspire.</p>
    <button class="cta-btn">Explore More</button>
  </section>
  
  <!-- Dynamic Content Section -->
  <section class="dynamic-content">
    <h2>Latest Updates</h2>
    <div id="api-content">Loading...</div>
  </section>
  
  <!-- Footer -->
  <footer>
    <p>&copy; 2025 RocketAir Clone. All rights reserved.</p>
  </footer>
  
  <!-- JavaScript -->
  <script>
    document.addEventListener("DOMContentLoaded", function() {
      // Animate header and hero elements using GSAP
      gsap.from("header", { duration: 1, y: -50, opacity: 0, ease: "power2.out" });
      gsap.to(".hero h1", { duration: 1, opacity: 1, y: -20, ease: "power2.out", delay: 0.5 });
      gsap.to(".hero p", { duration: 1, opacity: 1, y: -20, ease: "power2.out", delay: 0.7 });
      
      // Add click event to CTA button
      document.querySelector(".cta-btn").addEventListener("click", function() {
        alert("Explore RocketAir's digital experience!");
      });
      
      // Fetch and display dynamic content from a dummy API
      fetch("https://jsonplaceholder.typicode.com/posts?_limit=3")
        .then(response => response.json())
        .then(data => {
          const contentDiv = document.getElementById("api-content");
          contentDiv.innerHTML = data.map(post =>
            <p><strong>${post.title}</strong>: ${post.body}</p>
          ).join("");
        })
        .catch(error => console.error("Error fetching API data:", error));
    });
  </script>
</body>
</html>
