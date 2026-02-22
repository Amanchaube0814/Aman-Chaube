# Aman-Chaube
Data Sharing Link
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Your Photography</title>
  <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;1,300;1,400&family=Montserrat:wght@300;400;500;600&display=swap" rel="stylesheet" />
  <style>
    :root {
      --gold: #c9a84c;
      --gold-light: #e8d08a;
      --dark: #0a0a0a;
      --dark2: #111111;
      --cream: #f5f0e8;
      --text-light: #d4c9a8;
    }

    * { margin: 0; padding: 0; box-sizing: border-box; }

    body {
      background: var(--dark);
      color: var(--cream);
      font-family: 'Montserrat', sans-serif;
      overflow-x: hidden;
    }

    /* ── HERO ── */
    .hero {
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      position: relative;
      background: radial-gradient(ellipse at 50% 60%, #1a1408 0%, #0a0a0a 70%);
      overflow: hidden;
    }

    .hero::before {
      content: '';
      position: absolute;
      inset: 0;
      background: url("data:image/svg+xml,%3Csvg width='60' height='60' viewBox='0 0 60 60' xmlns='http://www.w3.org/2000/svg'%3E%3Cg fill='none' fill-rule='evenodd'%3E%3Cg fill='%23c9a84c' fill-opacity='0.03'%3E%3Cpath d='M36 34v-4h-2v4h-4v2h4v4h2v-4h4v-2h-4zm0-30V0h-2v4h-4v2h4v4h2V6h4V4h-4zM6 34v-4H4v4H0v2h4v4h2v-4h4v-2H6zM6 4V0H4v4H0v2h4v4h2V6h4V4H6z'/%3E%3C/g%3E%3C/g%3E%3C/svg%3E");
      opacity: 0.4;
    }

    .hero-content { text-align: center; z-index: 1; animation: fadeInUp 1.2s ease both; }

    .brand-name {
      font-family: 'Cormorant Garamond', serif;
      font-size: clamp(3rem, 10vw, 7rem);
      font-weight: 300;
      letter-spacing: 0.1em;
      color: var(--cream);
      line-height: 1;
    }

    .brand-name span {
      display: block;
      font-style: italic;
      color: var(--gold);
    }

    .tagline {
      font-size: clamp(0.65rem, 1.5vw, 0.85rem);
      letter-spacing: 0.4em;
      text-transform: uppercase;
      color: var(--text-light);
      margin-top: 1rem;
    }

    .gold-line {
      width: 80px;
      height: 1px;
      background: linear-gradient(to right, transparent, var(--gold), transparent);
      margin: 1.5rem auto;
    }

    /* ── WELCOME ── */
    .welcome-section {
      padding: 5rem 2rem 2rem;
      text-align: center;
    }

    .welcome-section h2 {
      font-family: 'Cormorant Garamond', serif;
      font-size: clamp(1.8rem, 4vw, 3rem);
      font-weight: 300;
      letter-spacing: 0.15em;
      color: var(--cream);
    }

    .welcome-section h2 em {
      font-style: italic;
      color: var(--gold);
    }

    /* ── GALLERY / VIDEO CARDS ── */
    .gallery {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 2rem;
      padding: 3rem 2rem 5rem;
      max-width: 400%;
      height: auto;
      margin: auto;
    }

    .card {
      position: relative;
      width: auto;
      cursor: pointer;
      overflow: hidden;
      border: 1px solid rgba(201,168,76,0.2);
      background: #0f0f0f;
      transition: transform 0.4s ease, box-shadow 0.4s ease;
      animation: fadeInUp 1s ease both;
    }

    .card:nth-child(2) { animation-delay: 0.2s; }

    .card:hover {
      transform: translateY(-6px);
      box-shadow: 0 20px 60px rgba(201,168,76,0.15);
    }

    .card-media {
      width: 100%;
      aspect-ratio: 2/4;
      object-fit: cover;
      display: block;
      transition: transform 0.6s ease;
    }

    .card:hover .card-media { transform: scale(1.04); }

    /* Placeholder when no image is set */
    .card-placeholder {
      width: 100%;
      aspect-ratio: 3/4;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      background: #141414;
      color: rgba(201,168,76,0.4);
      font-size: 0.75rem;
      letter-spacing: 0.2em;
      text-transform: uppercase;
      gap: 1rem;
      cursor: default;
    }

    .card-placeholder svg { opacity: 0.4; }

    .card-overlay {
      position: absolute;
      inset: 0;
      background: linear-gradient(to top, rgba(0,0,0,0.7) 0%, transparent 50%);
      display: flex;
      align-items: flex-end;
      padding: 1.5rem;
      opacity: 0;
      transition: opacity 0.4s;
    }

    .card:hover .card-overlay { opacity: 1; }

    .play-btn {
      width: 52px; height: 52px;
      border-radius: 50%;
      background: rgba(201,168,76,0.9);
      display: flex; align-items: center; justify-content: center;
      margin-left: auto;
    }

    .play-btn svg { margin-left: 4px; }

    .card-label {
      font-size: 0.75rem;
      letter-spacing: 0.25em;
      text-transform: uppercase;
      color: var(--gold-light);
      font-weight: 500;
    }

    /* ── INSTRUCTIONS NOTE ── */
    .note {
      background: rgba(201,168,76,0.06);
      border: 1px dashed rgba(201,168,76,0.3);
      border-radius: 4px;
      max-width: 680px;
      margin: 0 auto 4rem;
      padding: 1.5rem 2rem;
      font-size: 0.78rem;
      color: var(--text-light);
      line-height: 1.8;
      letter-spacing: 0.03em;
    }

    .note strong { color: var(--gold); }

    /* ── DIVIDER ── */
    .divider {
      width: 100%;
      height: 1px;
      background: linear-gradient(to right, transparent, rgba(201,168,76,0.3), transparent);
      margin: 2rem 0;
    }

    /* ── CONTACT ── */
    .contact {
      background: var(--dark2);
      padding: 5rem 2rem 3rem;
      text-align: center;
    }

    .contact h2 {
      font-family: 'Cormorant Garamond', serif;
      font-size: clamp(1.5rem, 4vw, 2.5rem);
      font-weight: 300;
      letter-spacing: 0.2em;
      color: var(--cream);
      margin-bottom: 0.5rem;
    }

    .contact h2 em { font-style: italic; color: var(--gold); }

    .contact-info {
      margin: 2rem auto;
      max-width: 420px;
    }

    .contact-info p {
      font-size: 0.82rem;
      letter-spacing: 0.1em;
      color: var(--text-light);
      line-height: 2;
    }

    .phone {
      font-size: 1rem;
      color: var(--gold);
      letter-spacing: 0.15em;
      margin: 0.5rem 0;
    }

    .cta-btn {
      display: inline-block;
      margin-top: 2rem;
      padding: 1rem 2.5rem;
      background: transparent;
      border: 1px solid var(--gold);
      color: var(--gold);
      font-family: 'Montserrat', sans-serif;
      font-size: 0.75rem;
      font-weight: 600;
      letter-spacing: 0.3em;
      text-transform: uppercase;
      text-decoration: none;
      position: relative;
      overflow: hidden;
      transition: color 0.3s ease;
    }

    .cta-btn::before {
      content: '';
      position: absolute;
      inset: 0;
      background: var(--gold);
      transform: scaleX(0);
      transform-origin: left;
      transition: transform 0.3s ease;
      z-index: -1;
    }

    .cta-btn:hover { color: var(--dark); }
    .cta-btn:hover::before { transform: scaleX(1); }

    /* ── FOOTER ── */
    footer {
      padding: 1.5rem;
      text-align: center;
      font-size: 0.65rem;
      letter-spacing: 0.25em;
      text-transform: uppercase;
      color: rgba(201,168,76,0.35);
      border-top: 1px solid rgba(201,168,76,0.08);
    }

    /* ── ANIMATION ── */
    @keyframes fadeInUp {
      from { opacity: 0; transform: translateY(30px); }
      to   { opacity: 1; transform: translateY(0); }
    }

    /* ── RESPONSIVE ── */
    @media (max-width: 600px) {
      .card { width: 90vw; }
    }
  </style>
</head>
<body>

  <!-- HERO -->
  <section class="hero">
    <div class="hero-content">
      <p class="tagline">Capturing Moments Forever</p>
      <div class="gold-line"></div>
      <h1 class="brand-name">
        Your Name
        <span>Photography</span>
      </h1>
      <div class="gold-line"></div>
      <p class="tagline">Est. 2024 &nbsp;·&nbsp; Every Story, Beautifully Told</p>
    </div>
  </section>

  <!-- WELCOME -->
  <section class="welcome-section">
    <h2>Welcome To <em>You</em></h2>
  </section>

  <!-- GALLERY CARDS -->
  <div class="gallery">

    <!-- CARD 1 — swap src and href -->
    <a class="card" href="https://drive.google.com/file/d/13nLNw_N-I6SnuNAKjtVhsPOHS-PTTkRs/view?usp=drive_link" target="_blank" rel="noopener">
      <!-- OPTION A: use an <img> tag with your photo -->
      <img src="C:\Users\i5 3gen home\Downloads\example.jpg" alt="Album Part 1" />

      <div class="card-overlay">
        <span class="card-label">Part 01 — Watch Video</span>
        <div class="play-btn">
          <svg width="18" height="18" viewBox="0 0 24 24" fill="white"><polygon points="5 3 19 12 5 21 5 3"/></svg>
        </div>
      </div>
    </a>


  </div>

  <!-- CONTACT -->
  <section class="contact">
    <h2>Contact <em>Us</em></h2>
    <div class="gold-line"></div>
    <div class="contact-info">
      <!-- Update address below -->
      <p>E-39, 16th Cross Street, Elliot's Beach</p>
      <!-- Update phone numbers below -->
      <p class="phone">+91 9876543210 &nbsp; &nbsp</p>
    </div>
    <!-- Update the WhatsApp number and message below -->
    <a class="cta-btn" href="https://wa.me/919876543210?text=Hello%20I%20Want%20To%20Book%20My%20Function" target="_blank" rel="noopener">
      Book My Function
    </a>
  </section>

  <div class="divider"></div>

  <footer>
    Copyright Reserved &copy; <span id="yr"></span> Your Photography
  </footer>

  <script>
    document.getElementById('yr').textContent = new Date().getFullYear();
  </script>
</body>
</html>
