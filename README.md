<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Sarah J's Bistro</title>
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <link href="https://fonts.googleapis.com/css2?family=Baloo+2:wght@400;600;700&display=swap" rel="stylesheet">

  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: "Baloo 2", system-ui, sans-serif;
      background: #f8f1e7;
      color: #3b2a26;
      line-height: 1.6;
    }

    img {
      max-width: 100%;
      display: block;
    }

    a {
      text-decoration: none;
      color: inherit;
    }

    .container {
      width: 90%;
      max-width: 1100px;
      margin: 0 auto;
    }

    /* HEADER / NAV */
    header {
      position: sticky;
      top: 0;
      z-index: 100;
      background: rgba(248, 241, 231, 0.96);
      backdrop-filter: blur(6px);
      border-bottom: 2px solid #e0c7b0;
    }

    .nav {
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 0.6rem 0;
    }

    .logo {
      font-size: 1.5rem;
      font-weight: 700;
      color: #c0392b;
      letter-spacing: 0.04em;
    }

    .logo span {
      color: #6b2c1a;
    }

    .nav-links {
      display: flex;
      gap: 1.3rem;
      font-size: 0.95rem;
    }

    .nav-links a {
      position: relative;
      font-weight: 600;
      color: #6b2c1a;
    }

    .nav-links a::after {
      content: "";
      position: absolute;
      left: 0;
      bottom: -2px;
      width: 0;
      height: 2px;
      background: #c0392b;
      transition: width 0.2s ease;
    }

    .nav-links a:hover::after {
      width: 100%;
    }

    section {
      padding: 2.5rem 0;
    }

    .section-title {
      text-align: center;
      font-size: 1.8rem;
      color: #3b1e14;
      margin-bottom: 0.4rem;
    }

    .section-subtitle {
      text-align: center;
      font-size: 0.95rem;
      color: #8d6c5e;
      margin-bottom: 1.9rem;
    }

    /* HERO */
    .hero {
      display: grid;
      grid-template-columns: minmax(0, 3fr) minmax(0, 2.5fr);
      gap: 1.8rem;
      align-items: center;
      padding-top: 2rem;
    }

    .hero-text {
      display: flex;
      flex-direction: column;
      gap: 0.5rem;
    }

    .hero-badge {
      display: inline-block;
      background: #c0392b;
      color: #fffaf4;
      font-size: 0.8rem;
      padding: 0.25rem 0.75rem;
      border-radius: 999px;
      letter-spacing: 0.06em;
      text-transform: uppercase;
    }

    .hero-text h1 {
      font-size: 2.5rem;
      line-height: 1.1;
      color: #3b1e14;
    }

    .hero-text h1 span {
      color: #c0392b;
    }

    .hero-tagline {
      font-size: 1.02rem;
      color: #7a5a4f;
      margin-top: 0.3rem;
    }

    .hero-buttons {
      display: flex;
      flex-wrap: wrap;
      gap: 0.6rem;
      margin-top: 0.9rem;
    }

    .btn {
      padding: 0.7rem 1.4rem;
      border-radius: 999px;
      border: none;
      cursor: pointer;
      font-size: 0.92rem;
      font-weight: 600;
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 0.3rem;
      box-shadow: 0 4px 12px rgba(0, 0, 0, 0.09);
      transition: transform 0.15s ease, box-shadow 0.15s ease, background 0.15s ease;
      white-space: nowrap;
    }

    .btn-primary {
      background: #c0392b;
      color: #fff9f1;
    }

    .btn-primary:hover {
      background: #a63022;
      transform: translateY(-1px);
      box-shadow: 0 6px 18px rgba(0, 0, 0, 0.14);
    }

    .btn-secondary {
      background: #fdf2e8;
      color: #6b2c1a;
    }

    .btn-secondary:hover {
      background: #fbe2c7;
      transform: translateY(-1px);
      box-shadow: 0 6px 18px rgba(0, 0, 0, 0.14);
    }

    .hero-media {
      position: relative;
    }

    .hero-main {
      border-radius: 1.3rem;
      overflow: hidden;
      border: 6px solid #fff;
      box-shadow: 0 10px 26px rgba(0, 0, 0, 0.18);
    }

    .hero-stack {
      position: absolute;
      width: 55%;
      left: 18px;
      bottom: -16px;
      border-radius: 1rem;
      overflow: hidden;
      border: 4px solid #fff8ee;
      box-shadow: 0 8px 20px rgba(0, 0, 0, 0.18);
    }

    .hero-tag {
      position: absolute;
      top: 12px;
      right: 16px;
      background: #fff8ee;
      padding: 0.35rem 0.8rem;
      font-size: 0.78rem;
      border-radius: 999px;
      box-shadow: 0 4px 10px rgba(0, 0, 0, 0.12);
      color: #c0392b;
    }

    /* ABOUT */
    .about {
      display: grid;
      grid-template-columns: minmax(0, 1.1fr) minmax(0, 1fr);
      gap: 1.6rem;
      align-items: center;
    }

    .about-text p {
      font-size: 0.98rem;
      color: #5d4236;
      margin-bottom: 0.7rem;
    }

    .about-photo-grid {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 0.7rem;
    }

    .about-photo-grid img {
      border-radius: 0.9rem;
      border: 4px solid #fff7ee;
      box-shadow: 0 6px 14px rgba(0, 0, 0, 0.12);
      height: 100%;
      object-fit: cover;
    }

    /* MENU & REVIEWS CARDS */
    .menu-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
      gap: 1.3rem;
    }

    .menu-card {
      background: #fffaf4;
      border-radius: 1.05rem;
      padding: 1.1rem 1.2rem;
      border: 1px solid #f1d8c2;
      box-shadow: 0 6px 14px rgba(0, 0, 0, 0.08);
      font-size: 0.95rem;
      color: #5c4033;
    }

    .menu-tag {
      font-size: 0.78rem;
      text-transform: uppercase;
      letter-spacing: 0.07em;
      color: #a06e4d;
      margin-bottom: 0.15rem;
    }

    .menu-card h3 {
      font-size: 1.1rem;
      color: #c0392b;
      margin-bottom: 0.25rem;
    }

    /* GALLERY */
    .gallery-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(170px, 1fr));
      gap: 0.85rem;
    }

    .gallery-grid figure {
      border-radius: 1rem;
      overflow: hidden;
      border: 4px solid #fff7ee;
      box-shadow: 0 6px 16px rgba(0, 0, 0, 0.15);
      position: relative;
    }

    .gallery-grid figcaption {
      position: absolute;
      left: 0;
      right: 0;
      bottom: 0;
      padding: 0.35rem 0.6rem;
      font-size: 0.8rem;
      background: linear-gradient(to top, rgba(0, 0, 0, 0.7), transparent);
      color: #fdf6ec;
    }

    /* VISIT */
    .visit-layout {
      display: grid;
      grid-template-columns: minmax(0, 1.1fr) minmax(0, 1fr);
      gap: 1.6rem;
      align-items: flex-start;
    }

    .visit-card {
      background: #fffaf4;
      border-radius: 1.05rem;
      padding: 1.2rem 1.3rem;
      border: 1px solid #f1d8c2;
      box-shadow: 0 6px 14px rgba(0, 0, 0, 0.08);
      font-size: 0.95rem;
    }

    .visit-card h3 {
      font-size: 1.15rem;
      color: #c0392b;
      margin-bottom: 0.45rem;
    }

    .hours-grid {
      display: grid;
      grid-template-columns: repeat(2, minmax(0, 1fr));
      gap: 0.2rem 0.7rem;
      font-size: 0.9rem;
      margin-top: 0.25rem;
    }

    .map-placeholder {
      border-radius: 1.05rem;
      padding: 1.6rem 1.2rem;
      background: #fdf2e8;
      border: 2px dashed #d9a67b;
      text-align: center;
      font-size: 0.9rem;
      color: #6e4a38;
      cursor: pointer;
      box-shadow: 0 5px 14px rgba(0, 0, 0, 0.06);
    }

    .map-placeholder strong {
      display: block;
      margin-bottom: 0.25rem;
    }

    footer {
      padding: 1.5rem 0 2rem;
      text-align: center;
      font-size: 0.85rem;
      color: #8f6c5b;
    }

    /* MOBILE / TABLET RESPONSIVE */
    @media (max-width: 900px) {
      .hero {
        grid-template-columns: 1fr;
      }

      .hero-media {
        order: -1;
      }
    }

    @media (max-width: 768px) {
      .nav-links {
        display: none; /* simple mobile nav: hide links */
      }

      .hero {
        padding-top: 1.4rem;
      }

      /* Hero image more “full” on mobile */
      .hero-main img {
        border-radius: 0.4rem;
      }

      .hero-stack {
        width: 55%;
        left: 10px;
        bottom: -14px;
      }

      .about,
      .visit-layout {
        grid-template-columns: 1fr;
      }

      .about-photo-grid {
        grid-template-columns: 1fr 1fr;
      }
    }

    @media (max-width: 540px) {
      .hero-text h1 {
        font-size: 2.05rem;
      }

      .hero-main img {
        border-radius: 0;          /* almost edge-to-edge look */
      }

      .container {
        width: 94%;
      }

      .gallery-grid {
        grid-template-columns: repeat(2, minmax(0, 1fr));
      }
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
    <div class="hero-text">
      <div class="hero-badge">Local Favorite • From-Scratch Comfort Food</div>
      <h1>Welcome to <span>Sarah J's Bistro</span></h1>
      <p class="hero-tagline">
        Crispy fish, cozy breakfasts, burgers & warm pastries — your new go-to spot in town.
      </p>

      <div class="hero-buttons">
        <button class="btn btn-primary"
          onclick="document.getElementById('menu').scrollIntoView({behavior:'smooth'})">
          View Menu
        </button>
        <button class="btn btn-secondary"
          onclick="document.getElementById('visit').scrollIntoView({behavior:'smooth'})">
          Hours & Location
        </button>
      </div>
    </div>

    <div class="hero-media">
      <div class="hero-main">
        <img src="https://raw.githubusercontent.com/Bakerreniya/Sarah-J-s-Bistro/bfe0c2df40785c32e42d11a5d9ad2966c170f095/IMG_6784.jpeg"
             alt="Plates of food at Sarah J's Bistro">
      </div>
      <div class="hero-stack">
        <img src="https://raw.githubusercontent.com/Bakerreniya/Sarah-J-s-Bistro/e6ce96ca6e1f0f6d4097d8e0450339c13be59768/IMG_6780.jpeg"
             alt="Food close-up at Sarah J's Bistro">
      </div>
      <div class="hero-tag">
        ♥ Family-run • Made with love
      </div>
    </div>
  </section>

  <!-- ABOUT -->
  <section id="about">
    <div class="container about">
      <div class="about-text">
        <h2 class="section-title">Homestyle Feel, Bistro Flavor</h2>
        <p>
          At <strong>Sarah J’s Bistro</strong>, everything tastes like comfort. Fresh, hot plates
          made with care every day — from big breakfasts to satisfying dinners.
        </p>
        <p>
          Enjoy fluffy pancakes, crispy fried favorites, stacked burgers, and desserts that taste
          like home. Whether you’re starting your morning or ending your day, we’ve got a plate
          waiting for you.
        </p>
      </div>

      <div class="about-photo-grid">
        <img src="https://raw.githubusercontent.com/Bakerreniya/Sarah-J-s-Bistro/e6ce96ca6e1f0f6d4097d8e0450339c13be59768/IMG_6781.jpeg"
             alt="Breakfast or lunch plate at Sarah J's Bistro">
        <img src="https://raw.githubusercontent.com/Bakerreniya/Sarah-J-s-Bistro/e6ce96ca6e1f0f6d4097d8e0450339c13be59768/IMG_6782.jpeg"
             alt="Hearty meal at Sarah J's Bistro">
      </div>
    </div>
  </section>

  <!-- MENU -->
  <section id="menu">
    <div class="container">
      <h2 class="section-title">Our Menu</h2>
      <p class="section-subtitle">A small taste of what we’re serving today.</p>

      <div class="menu-grid">
        <article class="menu-card">
          <div class="menu-tag">Breakfast</div>
          <h3>Morning Favorites</h3>
          <p>
            Pancakes, eggs, sausage, bacon, home fries and more — the kind of breakfast that
            keeps you full and happy.
          </p>
        </article>

        <article class="menu-card">
          <div class="menu-tag">Lunch & Dinner</div>
          <h3>Comfort Plates</h3>
          <p>
            Burgers, fish & chips, sandwiches, fries and onion rings — crispy, filling, and made
            to order.
          </p>
        </article>

        <article class="menu-card">
          <div class="menu-tag">Bakery</div>
          <h3>Sweets</h3>
          <p>
            Fresh pastries, cinnamon rolls, cookies and more rotating treats. Check the case to
            see what’s just come out.
          </p>
        </article>
      </div>
    </div>
  </section>

  <!-- REVIEWS -->
  <section id="reviews">
    <div class="container">
      <h2 class="section-title">Customer Reviews</h2>
      <p class="section-subtitle">Real thoughts from our guests.</p>

      <div class="menu-grid">
        <article class="menu-card">
          <div class="menu-tag">★★★★★</div>
          <h3>ryu taski</h3>
          <p>
            “Easily 5 stars across the board. Small place, HUGE flavor.
            Amazing menu, large portions, great prices!”
          </p>
          <p style="font-size:0.8rem; color:#a06e4d;">Dinner • $10–20</p>
        </article>

        <article class="menu-card">
          <div class="menu-tag">★★★★★</div>
          <h3>Tatiana Porsch</h3>
          <p>
            “The new menu is awesome! The shrimp poke bowl is delicious and the
            relaxing vibe makes it the best in town.”
          </p>
          <p style="font-size:0.8rem; color:#a06e4d;">$20–30</p>
        </article>

        <article class="menu-card">
          <div class="menu-tag">★★★★★</div>
          <h3>Vince Battista</h3>
          <p>
            “Great dinner at Sarah J's! Loved the BLT and French Dip with fries.
            The au jus is incredible!”
          </p>
          <p style="font-size:0.8rem; color:#a06e4d;">Dinner • $20–30</p>
        </article>
      </div>
    </div>
  </section>

  <!-- GALLERY -->
  <section id="gallery">
    <div class="container">
      <h2 class="section-title">Gallery</h2>
      <p class="section-subtitle">A peek inside Sarah J’s Bistro.</p>

      <div class="gallery-grid">
        <!-- Existing images -->
        <figure>
          <img src="https://raw.githubusercontent.com/Bakerreniya/Sarah-J-s-Bistro/e6ce96ca6e1f0f6d4097d8e0450339c13be59768/IMG_6783.jpeg"
               alt="Dining and interior at Sarah J's Bistro">
          <figcaption>Dining & Atmosphere</figcaption>
        </figure>

        <figure>
          <img src="https://raw.githubusercontent.com/Bakerreniya/Sarah-J-s-Bistro/e6ce96ca6e1f0f6d4097d8e0450339c13be59768/IMG_6781.jpeg"
               alt="Plate of food at Sarah J's Bistro">
          <figcaption>Fresh & Hot Plates</figcaption>
        </figure>

        <!-- New images -->
        <figure>
          <img src="https://raw.githubusercontent.com/Bakerreniya/Sarah-J-s-Bistro/241e8270562da48d9fbdeaed34b0bd44f6175477/IMG_6791.jpeg"
               alt="Customer favorite dishes at Sarah J's Bistro">
          <figcaption>Customer Favorites</figcaption>
        </figure>

        <figure>
          <img src="https://raw.githubusercontent.com/Bakerreniya/Sarah-J-s-Bistro/241e8270562da48d9fbdeaed34b0bd44f6175477/IMG_6789.jpeg"
               alt="Daily special plate at Sarah J's Bistro">
          <figcaption>Daily Specials</figcaption>
        </figure>

        <figure>
          <img src="https://raw.githubusercontent.com/Bakerreniya/Sarah-J-s-Bistro/241e8270562da48d9fbdeaed34b0bd44f6175477/IMG_6788.jpeg"
               alt="Signature dish at Sarah J's Bistro">
          <figcaption>Signature Dishes</figcaption>
        </figure>

        <figure>
          <img src="https://raw.githubusercontent.com/Bakerreniya/Sarah-J-s-Bistro/241e8270562da48d9fbdeaed34b0bd44f6175477/IMG_6787.jpeg"
               alt="Restaurant moment at Sarah J's Bistro">
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
        <p><strong>Phone:</strong> (000) 000-0000</p>

        <p style="margin-top:0.6rem;"><strong>Hours:</strong></p>
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
        🗺️
        <strong>Open in Google Maps</strong>
        <p>Tap to view our location and get directions.</p>
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
