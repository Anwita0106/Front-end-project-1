# Front-end-project-1
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>RocketAir Clone</title>
    <link rel="stylesheet" href="styles.css">
    <script defer src="script.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/gsap.min.js"></script>
</head>
<body>
    <header>
        <nav class="navbar">
            <div class="logo">RocketAir</div>
            <ul class="nav-links">
                <li><a href="#">Home</a></li>
                <li><a href="#">Services</a></li>
                <li><a href="#">Projects</a></li>
                <li><a href="#">Contact</a></li>
            </ul>
        </nav>
    </header>

    <section class="hero">
        <h1>Welcome to RocketAir</h1>
        <p>Creative digital experiences that inspire.</p>
        <button class="cta-btn">Explore More</button>
    </section>

    <section class="dynamic-content">
        <h2>Latest Updates</h2>
        <div id="api-content">Loading...</div>
    </section>

    <footer>
        <p>&copy; 2025 RocketAir Clone. All rights reserved.</p>
    </footer>
</body>
</html>
/* General Styles */
body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
    background: #111;
    color: #fff;
    text-align: center;
}

/* Navbar */
.navbar {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 15px 30px;
    background: rgba(0, 0, 0, 0.8);
    position: fixed;
    width: 100%;
    top: 0;
}

.logo {
    font-size: 24px;
    font-weight: bold;
}

.nav-links {
    list-style: none;
    display: flex;
}

.nav-links li {
    margin: 0 15px;
}

.nav-links a {
    text-decoration: none;
    color: white;
    font-size: 18px;
}

/* Hero Section */
.hero {
    height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    background: url('assets/hero-bg.jpg') no-repeat center center/cover;
}

.hero h1 {
    font-size: 48px;
    animation: fadeIn 2s ease-in-out;
}

.hero p {
    font-size: 20px;
    margin: 15px 0;
}

.cta-btn {
    padding: 12px 25px;
    font-size: 18px;
    background: orangered;
    color: white;
    border: none;
    cursor: pointer;
    transition: 0.3s;
}

.cta-btn:hover {
    background: red;
}

/* Footer */
footer {
    background: rgba(0, 0, 0, 0.9);
    padding: 20px;
    position: fixed;
    width: 100%;
    bottom: 0;
}

/* Animations */
@keyframes fadeIn {
    from { opacity: 0; transform: translateY(-20px); }
    to { opacity: 1; transform: translateY(0); }
}
document.addEventListener("DOMContentLoaded", () => {
    // GSAP Animation
    gsap.from(".navbar", { duration: 1, y: -50, opacity: 0, ease: "power2.out" });
    gsap.from(".hero h1", { duration: 1.5, y: 50, opacity: 0, delay: 0.5, ease: "power2.out" });

    // Button Click Effect
    document.querySelector(".cta-btn").addEventListener("click", () => {
        alert("Explore RocketAir's digital experience!");
    });

    // Fetch API Content (Dummy API)
    fetch("https://jsonplaceholder.typicode.com/posts?_limit=3")
        .then(response => response.json())
        .then(data => {
            const contentDiv = document.getElementById("api-content");
            contentDiv.innerHTML = data.map(post => `<p><strong>${post.title}</strong>: ${post.body}</p>`).join("");
        })
        .catch(error => console.error("Error fetching API data:", error));
});
