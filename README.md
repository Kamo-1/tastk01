# tastk01
HTML-tastk

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>My Portfolio</title>
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700;900&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet"/>
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --ink: #0e0e0e;
      --paper: #f5f0e8;
      --accent: #c84b2f;
      --muted: #7a7469;
      --card: #ede8df;
    }

    html { scroll-behavior: smooth; }

    body {
      font-family: 'DM Sans', sans-serif;
      background: var(--paper);
      color: var(--ink);
      line-height: 1.6;
    }

    /* ── NAV ── */
    nav {
      position: sticky; top: 0; z-index: 100;
      display: flex; align-items: center; justify-content: space-between;
      padding: 1rem 2.5rem;
      background: var(--paper);
      border-bottom: 1.5px solid var(--ink);
    }

    .logo {
      font-family: 'Playfair Display', serif;
      font-size: 1.4rem; font-weight: 900;
      letter-spacing: -0.5px;
      border: 2px solid var(--ink);
      padding: 0.25rem 0.75rem;
      text-decoration: none; color: var(--ink);
    }

    .nav-links { display: flex; gap: 2rem; list-style: none; }
    .nav-links a {
      text-decoration: none; color: var(--ink);
      font-size: 0.95rem; font-weight: 500;
      letter-spacing: 0.03em;
      position: relative;
      padding-bottom: 2px;
    }
    .nav-links a::after {
      content: ''; position: absolute; bottom: 0; left: 0;
      width: 0; height: 1.5px; background: var(--accent);
      transition: width 0.25s ease;
    }
    .nav-links a:hover::after { width: 100%; }

    /* ── HERO ── */
    #home {
      min-height: 85vh;
      display: flex; align-items: center; justify-content: center;
      border-bottom: 1.5px solid var(--ink);
      padding: 3rem 2.5rem;
      background:
        repeating-linear-gradient(
          0deg,
          transparent, transparent 39px,
          rgba(14,14,14,0.07) 39px, rgba(14,14,14,0.07) 40px
        ),
        var(--paper);
      text-align: center;
      animation: fadeIn 0.8s ease both;
    }

    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(18px); }
      to   { opacity: 1; transform: translateY(0); }
    }

    .hero-media {
      width: min(700px, 100%);
      aspect-ratio: 16/9;
      border: 2px solid var(--ink);
      background: var(--card);
      display: flex; align-items: center; justify-content: center;
      color: var(--muted); font-size: 0.9rem;
      margin: 0 auto 2rem;
      overflow: hidden;
      position: relative;
    }

    /* A decorative placeholder – swap src for a real video/image */
    .hero-media video,
    .hero-media img {
      width: 100%; height: 100%; object-fit: cover;
    }

    .media-placeholder {
      display: flex; flex-direction: column; align-items: center; gap: 0.75rem;
    }

    .media-placeholder svg { opacity: 0.35; }

    .hero-media-label {
      font-size: 0.85rem; color: var(--muted);
    }

    /* ── ABOUT SECTION ── */
    #about {
      display: grid;
      grid-template-columns: 1fr auto;
      gap: 3rem;
      padding: 4rem 2.5rem;
      border-bottom: 1.5px solid var(--ink);
      animation: fadeIn 0.9s ease 0.1s both;
    }

    .about-text h1 {
      font-family: 'Playfair Display', serif;
      font-size: clamp(2rem, 5vw, 3.5rem);
      font-weight: 900;
      line-height: 1.1;
      margin-bottom: 1.25rem;
    }

    .about-text h1 span { color: var(--accent); }

    .about-text p {
      font-size: 1rem; color: #333;
      max-width: 520px;
      margin-bottom: 1rem;
    }

    .about-photo {
      width: 180px; height: 180px;
      border-radius: 50%;
      border: 3px solid var(--ink);
      background: var(--card);
      overflow: hidden;
      display: flex; align-items: center; justify-content: center;
      color: var(--muted); font-size: 0.8rem; text-align: center;
      flex-shrink: 0;
      align-self: center;
    }

    .about-photo img { width: 100%; height: 100%; object-fit: cover; }

    /* ── CONTACT PAGE ── */
    #contact {
      padding: 4rem 2.5rem;
      border-bottom: 1.5px solid var(--ink);
      animation: fadeIn 0.9s ease 0.15s both;
    }

    #contact h2 {
      font-family: 'Playfair Display', serif;
      font-size: 2rem; margin-bottom: 1.5rem;
    }

    .contact-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 2.5rem;
      align-items: start;
    }

    .contact-info p { margin-bottom: 0.6rem; font-size: 0.95rem; }
    .contact-info strong { color: var(--accent); }

    .contact-form { display: flex; flex-direction: column; gap: 0.85rem; }

    .contact-form input,
    .contact-form textarea {
      width: 100%;
      padding: 0.75rem 1rem;
      border: 1.5px solid var(--ink);
      background: transparent;
      font-family: 'DM Sans', sans-serif;
      font-size: 0.95rem;
      color: var(--ink);
      outline: none;
      transition: border-color 0.2s;
      resize: vertical;
    }

    .contact-form input:focus,
    .contact-form textarea:focus { border-color: var(--accent); }

    .contact-form button {
      align-self: flex-start;
      padding: 0.7rem 2rem;
      background: var(--ink);
      color: var(--paper);
      border: none; cursor: pointer;
      font-family: 'DM Sans', sans-serif;
      font-size: 0.95rem; font-weight: 500;
      letter-spacing: 0.05em;
      transition: background 0.2s;
    }

    .contact-form button:hover { background: var(--accent); }

    /* ── FOOTER ── */
    footer {
      display: grid;
      grid-template-columns: 1fr 1fr 1fr;
      gap: 1.5rem;
      align-items: center;
      padding: 1.75rem 2.5rem;
      border-top: 1.5px solid var(--ink);
      background: var(--ink);
      color: var(--paper);
    }

    .footer-address { font-size: 0.85rem; line-height: 1.6; }
    .footer-address strong { display: block; margin-bottom: 0.25rem; color: var(--paper); }

    .footer-links { display: flex; flex-direction: column; gap: 0.35rem; }
    .footer-links a {
      color: var(--paper); text-decoration: none;
      font-size: 0.85rem; transition: color 0.2s;
    }
    .footer-links a:hover { color: #f0a090; }

    .footer-socials { display: flex; gap: 0.75rem; justify-content: flex-end; }

    .social-btn {
      width: 40px; height: 40px;
      border-radius: 50%;
      border: 1.5px solid var(--paper);
      display: flex; align-items: center; justify-content: center;
      color: var(--paper); text-decoration: none;
      font-size: 0.8rem; font-weight: 700;
      transition: background 0.2s, color 0.2s;
    }

    .social-btn:hover { background: var(--paper); color: var(--ink); }

    /* ── MAP PLACEHOLDER ── */
    .map-embed {
      width: 100%; aspect-ratio: 16/7;
      border: 1.5px solid var(--ink);
      background: var(--card);
      display: flex; align-items: center; justify-content: center;
      color: var(--muted); font-size: 0.85rem;
      margin-top: 1.5rem;
    }

    /* ── RESPONSIVE ── */
    @media (max-width: 700px) {
      #about { grid-template-columns: 1fr; }
      .about-photo { margin: 0 auto; }
      .contact-grid { grid-template-columns: 1fr; }
      footer { grid-template-columns: 1fr; text-align: center; }
      .footer-socials { justify-content: center; }
    }
  </style>
</head>
<body>

  <!-- ── NAVIGATION ── -->
  <nav>
    <a href="#home" class="logo">YN</a>
    <ul class="nav-links">
      <li><a href="#home">Home</a></li>
      <li><a href="#about">About Me</a></li>
      <li><a href="#contact">Contact Us</a></li>
    </ul>
  </nav>

  <!-- ── HOME / HERO ── -->
  <section id="home">
    <div>
      <div class="hero-media">
        
        <div class="media-placeholder">
          <svg width="64" height="64" viewBox="0 0 64 64" fill="none">
            <rect x="4" y="12" width="56" height="40" rx="3" stroke="#0e0e0e" stroke-width="2"/>
            <polygon points="26,22 26,42 44,32" fill="#0e0e0e" opacity="0.3"/>
          </svg>
          <video width="640" height="350" controls source src ="c:\Users\kamoz\Downloads\WhatsApp Video 2026-05-19 at 21.21.50.mp4" type="Vide/mp4"></video>
          
        </div>
      </div>
    </div>
  </section>

  <!-- ── ABOUT ME ── -->
  <section id="about">
    <div class="about-text">
      <h1>Kamogelo<span> Innocent</span> Sekgobela</h1>
      <p>
        <strong>Bio</strong> — I'm a Mathematical Sciences graduate with a passion for problem-solving and a love for all things tech.I'm the kind of person who enjoys breaking down complex problems and finding smart, practical solutions.
      </p>
      <p>
        When I'm not geeking out over tech, I'm always looking for new ways to grow and make an impact. I'm excited about what the future holds and ready to bring my skills to the table!
      </p>
    </div>
    <div class="about-photo">
      <!--Adding of a picture here. -->
        
        <img src="c:\Users\kamoz\Downloads\WhatsApp Image 2026-05-19 at 21.06.11.jpeg"/>
    </div>
  </section>

  <!-- ── CONTACT US ── -->
  <section id="contact">
    <h2>Contact Us</h2>
    <div class="contact-grid">

      <div class="contact-info">
        <p><strong>📍 Address:</strong> 10050 Trichardtsdal,Tzannen, South Africa</p>
        <p><strong>📞 Phone:</strong> +27 73 702 1253</p>
        <p><strong>✉️ Email:</strong> kamogeloinnocent19@email.com</p>
        <p style="margin-top:1rem; color: var(--muted); font-size:0.9rem;">
          Feel free to reach out for collaborations, opportunities, or just to say hello!
        </p>

        <!-- Embed your Google Map here -->
        <div class="map-embed">
          
          <a href="https://maps.app.goo.gl/7FwZSH5smTpYmgZV8?g_st=aw">Google Map</a>
          
        </div>
      </div>

      <form class="contact-form" onsubmit="return false;">
        <input type="text" placeholder="Your Name" required />
        <input type="email" placeholder="Your Email" required />
        <input type="text" placeholder="Subject" />
        <textarea rows="5" placeholder="Your message…" required></textarea>
        <button type="submit">Send Message</button>
      </form>

    </div>
  </section>

  <!-- ── FOOTER ── -->
  <footer>
    <div class="footer-address">
      <strong>Kamogelo Sekgobela</strong>
      10050,Trichardtsdal<br/>
      Tzaneen, South Africa<br/>
      📞 +27 (73) 792 1253
    </div>

    <div class="footer-links">
      <a href="#home">Home</a>
      <a href="#about">About Me</a>
      <a href="#contact">Contact Us</a>
    </div>

    <div class="footer-socials">
      <!-- T = Twitter/X, F = Facebook, I = Instagram -->
      <a href="#" class="social-btn" title="Twitter/X">𝕏</a>
      <a href="#" class="social-btn" title="Facebook">f</a>
      <a href="#" class="social-btn" title="Instagram">in</a>
    </div>
  </footer>

</body>
</html>
