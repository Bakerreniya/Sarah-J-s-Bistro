
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Sarah J's Bistro</title>
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <link href="https://fonts.googleapis.com/css2?family=Baloo+2:wght@400;600;700&display=swap" rel="stylesheet">

  <style>
    * { margin: 0; padding: 0; box-sizing: border-box; }
    body {
      font-family: "Baloo 2", sans-serif;
      background: #f8f1e7;
      color: #3b2a26;
      line-height: 1.6;
    }
    img { max-width: 100%; display: block; border-radius: 10px; }

    header {
      position: sticky;
      top: 0;
      background: rgba(248,241,231,0.95);
      backdrop-filter: blur(6px);
      padding: 10px 0;
      border-bottom: 2px solid #e0c7b0;
      z-index: 100;
    }

    .container {
      width: 90%;
      max-width: 1100px;
      margin: auto;
    }

    .nav { display: flex; justify-content: space-between; align-items: center; }
    .logo { font-size: 1.6rem; font-weight: 700; color: #c0392b; }
    .logo span { color: #6b2c1a; }

    .nav-links { display: flex; gap: 1.3rem; }
    .nav-links a { color: #6b2c1a; font-weight: 600; }

    section { padding: 2.5rem 0; }

    .section-title {
      font-size: 1.8rem;
      text-align: center;
      margin-bottom: 0.4rem;
      color: #3b1e14;
    }
    .section-subtitle {
      text-align: center;
      font-size: 0.95rem;
      color: #8d6c5e;
      margin-bottom: 2rem;
    }

    /* HERO */
    .hero {
      display: grid;
      grid-template-columns: 3fr 2fr;
      gap: 1.5rem;
      align-items: center;
    }
    .hero-badge {
      background: #c0392b;
      color: #fffaf4;
      padding: 4px 12px;
      border-radius: 30px;
      font-size: 0.8rem;
      margin-bottom: 10px;
      display: inline-block;
    }
    .hero-buttons { display: flex; gap: 10px; margin-top: 1rem; }

    .btn {
      padding: 8px 16px;
      border-radius: 30px;
      border: none;
      cursor: pointer;
      font-size: 0.9rem;
      font-weight: 600;
    }
    .btn-primary { background: #c0392b; color: #fff; }
    .btn-secondary { background: #f2dfd3; color: #6b2c1a; }

    .hero-photo-wrap { position: relative; }
    .hero-main img { border-radius: 20px; }
    .hero-stack {
      position: absolute;
      width: 55%;
      bottom: -20px;
      left: 20px;
      border: 4px solid white;
      border-radius: 15px;
    }

    /* ABOUT */
    .about {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 1.5rem;
    }
    .about-photo-grid img {
      border-radius: 12px;
      height: 100%;
      object-fit: cover;
    }
    .about-photo-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 0.7rem;
    }

    /* MENU + REVIEWS */
    .menu-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit,minmax(240px,1fr));
      gap: 1.3rem;
    }
    .menu-card {
      background: #fffaf4;
      border-radius: 15px;
      padding: 1.2rem;
      border: 1px solid #f1d8c2;
      box-shadow: 0 5px 14px rgba(0,0,0,0.08);
    }
    .menu-tag {
      font-size: 0.75rem;
      color: #a06e4d;
      margin-bottom: 4px;
    }
    .menu-card h3 { color: #c0392b; }

    /* GALLERY */
    .gallery-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit,minmax(180px,1fr));
      gap: 0.9rem;
    }
    figure { position: relative; }
    figcaption {
      position: absolute;
      bottom: 0;
      width: 100%;
      background: linear-gradient(to top,rgba(0,0,0,0.6),transparent);
      color: #fff;
      padding: 4px 8px;
      font-size: 0.8rem;
    }

    /* VISIT */
    .visit-layout {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 1.5rem;
    }
    .visit-card {
      background: #fffaf4;
      border-radius: 15px;
      padding: 1.2rem;
      border: 1px solid #f1d8c2;
    }
    .hours-grid {
      display: grid;
      grid-template-columns: repeat(2,1fr);
      margin-top: 0.4rem;
      gap: 4px;
    }

    .map-placeholder {
      border-radius: 15px;
      padding: 1.4rem;
      background: #fdf2e8;
      border: 2px dashed #d9a67b;
      text-align: center;
      cursor: pointer;
    }

    footer {
      padding: 1.5rem 0;
      text-align: center;
      font-size: 0.85rem;
      color: #8f6c5b;
    }

    @media(max-width:820px){
      .hero, .about, .visit-layout { grid-template-columns: 1fr; }
      .hero-photo-wrap { order: -1; }
    }
  </style>
</head>

<body>

<header>
  <div class="container nav">
    <div class="logo">Sarah J's <span>Bistro</span></div>
    <nav class="nav-links">
      <a href="#about">About</a>
      <a href="#menu">Menu</a>
      <a href="#reviews">Reviews</a>
      <a href="#gallery">Gallery</a>
      <a href="#visit">Visit</a>
    </nav>
  </div>
</header>

<main>

<!-- HERO -->
<section class="container hero">
  <div>
    <div class="hero-badge">Local Favorite • From-Scratch Comfort Food</div>
    <h1>Welcome to <span style="color:#c0392b;">Sarah J's Bistro</span></h1>
    <p class="hero-tagline">Crispy fish, cozy breakfasts, burgers & warm pastries — your new go-to spot.</p>

    <div class="hero-buttons">
      <button class="btn btn-primary" onclick="document.getElementById('menu').scrollIntoView({behavior:'smooth'})">View Menu</button>
      <button class="btn btn-secondary" onclick="document.getElementById('visit').scrollIntoView({behavior:'smooth'})">Hours & Location</button>
    </div>
  </div>

  <div class="hero-photo-wrap">
    <div class="hero-main">
      <img src="https://raw.githubusercontent.com/Bakerreniya/Sarah-J-s-Bistro/bfe0c2df40785c32e42d11a5d9ad2966c170f095/IMG_6784.jpeg">
    </div>

    <div class="hero-stack">
      <img src="https://raw.githubusercontent.com/Bakerreniya/Sarah-J-s-Bistro/e6ce96ca6e1f0f6d4097d8e0450339c13be59768/IMG_6780.jpeg">
    </div>

    <div class="hero-tag">♥ Family-run • Made with love</div>
  </div>
</section>

<!-- ABOUT -->
<section id="about">
  <div class="container about">

    <div>
      <h2 class="section-title">Homestyle Feel, Bistro Flavor</h2>
      <p>At Sarah J’s Bistro, everything tastes like comfort. Fresh, hot plates made with care daily.</p>
      <p>Enjoy big breakfasts, delicious lunch plates, and handmade pastries all in a cozy town-favorite spot.</p>
    </div>

    <div class="about-photo-grid">
      <img src="https://raw.githubusercontent.com/Bakerreniya/Sarah-J-s-Bistro/e6ce96ca6e1f0f6d4097d8e0450339c13be59768/IMG_6781.jpeg">
      <img src="https://raw.githubusercontent.com/Bakerreniya/Sarah-J-s-Bistro/e6ce96ca6e1f0f6d4097d8e0450339c13be59768/IMG_6782.jpeg">
    </div>

  </div>
</section>

<!-- MENU -->
<section id="menu">
  <div class="container">
    <h2 class="section-title">Our Menu</h2>
    <p class="section-subtitle">A taste of what we’re serving today.</p>

    <div class="menu-grid">
      <article class="menu-card">
        <div class="menu-tag">Breakfast</div>
        <h3>Morning Favorites</h3>
        <p>Pancakes, eggs, sausage, bacon, home fries & more.</p>
      </article>

      <article class="menu-card">
        <div class="menu-tag">Lunch & Dinner</div>
        <h3>Comfort Plates</h3>
        <p>Burgers, fish & chips, sandwiches, fries, onion rings.</p>
      </article>

      <article class="menu-card">
        <div class="menu-tag">Bakery</div>
        <h3>Sweets</h3>
        <p>Fresh pastries, cinnamon rolls, cookies & more daily.</p>
      </article>
    </div>
  </div>
</section>

<!-- REVIEWS -->
<section id="reviews">
  <div class="container">
    <h2 class="section-title">Customer Reviews</h2>
    <p class="section-subtitle">Real thoughts from our guests</p>

    <div class="menu-grid">

      <article class="menu-card">
        <div class="menu-tag">★★★★★</div>
        <h3>ryu taski</h3>
        <p>“Easily 5 stars across the board. Huge flavor, great prices, and an amazing menu!”</p>
      </article>

      <article class="menu-card">
        <div class="menu-tag">★★★★★</div>
        <h3>Tatiana Porsch</h3>
        <p>“The new menu is awesome! The shrimp poke bowl is delicious and the vibe is perfect.”</p>
      </article>

      <article class="menu-card">
        <div class="menu-tag">★★★★★</div>
        <h3>Vince Battista</h3>
        <p>“Loved the BLT and French Dip. The au jus is incredible!”</p>
      </article>

    </div>
  </div>
</section>

<!-- GALLERY -->
<section id="gallery">
  <div class="container">
    <h2 class="section-title">Gallery</h2>
    <p class="section-subtitle">Moments from around the bistro</p>

    <div class="gallery-grid">

      <!-- OLD -->
      <figure>
        <img src="https://raw.githubusercontent.com/Bakerreniya/Sarah-J-s-Bistro/e6ce96ca6e1f0f6d4097d8e0450339c13be59768/IMG_6783.jpeg">
        <figcaption>Dining & Atmosphere</figcaption>
      </figure>

      <figure>
        <img src="https://raw.githubusercontent.com/Bakerreniya/Sarah-J-s-Bistro/e6ce96ca6e1f0f6d4097d8e0450339c13be59768/IMG_6781.jpeg">
        <figcaption>Fresh & Hot Plates</figcaption>
      </figure>

      <!-- NEW -->
      <figure>
        <img src="https://raw.githubusercontent.com/Bakerreniya/Sarah-J-s-Bistro/241e8270562da48d9fbdeaed34b0bd44f6175477/IMG_6791.jpeg">
        <figcaption>Customer Favorites</figcaption>
      </figure>

      <figure>
        <img src="https://raw.githubusercontent.com/Bakerreniya/Sarah-J-s-Bistro/241e8270562da48d9fbdeaed34b0bd44f6175477/IMG_6789.jpeg">
        <figcaption>Daily Specials</figcaption>
      </figure>

      <figure>
        <img src="https://raw.githubusercontent.com/Bakerreniya/Sarah-J-s-Bistro/241e8270562da48d9fbdeaed34b0bd44f6175477/IMG_6788.jpeg">
        <figcaption>Signature Dishes</figcaption>
      </figure>

      <figure>
        <img src="https://raw.githubusercontent.com/Bakerreniya/Sarah-J-s-Bistro/241e8270562da48d9fbdeaed34b0bd44f6175477/IMG_6787.jpeg">
        <figcaption>Bistro Moments</figcaption>
      </figure>

    </div>
  </div>
</section>

<!-- VISIT -->
<section id="visit">
  <div class="container visit-layout">
    <div class="visit-card">
      <h3>Visit Us</h3>
      <p><strong>Address:</strong> 123 Main Street, YourTown, FL</p>

      <p><strong>Hours:</strong></p>
      <div class="hours-grid">
        <span>Monday</span><span>8:00 AM – 2:00 PM</span>
        <span>Tuesday</span><span>8:00 AM – 8:00 PM</span>
        <span>Wednesday</span><span>8:00 AM – 8:00 PM</span>
        <span>Thursday</span><span>8:00 AM – 8:00 PM</span>
        <span>Friday</span><span>8:00 AM – 8:00 PM</span>
        <span>Saturday</span><span>8:00 AM – 8:00 PM</span>
        <span>Sunday</span><span>8:00 AM – 2:00 PM</span>
      </div>
    </div>

    <div class="map-placeholder"
      onclick="window.open('https://maps.app.goo.gl/nx8Kiaw4UMQoo2ZXA','_blank')">
      🗺️ <br>
      <strong>Open in Google Maps</strong>
      <p>Tap to view our location</p>
    </div>

  </div>
</section>

</main>

<footer>
  © <span id="year"></span> Sarah J's Bistro • Made with love.
</footer>

<script>
  document.getElementById("year").textContent = new Date().getFullYear();
</script>

</body>
</html>
