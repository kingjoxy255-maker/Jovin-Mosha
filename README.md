<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>New Rose Garden Hall 🌹</title>
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;500;700&family=Inter:wght@300;400;500;600&display=swap" rel="stylesheet">
  <style>
    :root {
      /* Modern Neutral Color Palette */
      --primary-bg: #fafaf9;
      --secondary-bg: #f5f5f4;
      --accent-bg: #e7e5e4;
      --text-primary: #1c1917;
      --text-secondary: #57534e;
      --text-muted: #78716c;
      --warm-gray: #a8a29e;
      --sage-green: #84a59d;
      --cream: #f6f3f0;
      --charcoal: #292524;
      --soft-white: #fefefe;
      
      /* Dark mode colors */
      --dark-primary: #1c1917;
      --dark-secondary: #292524;
      --dark-accent: #44403c;
      --dark-text-primary: #fafaf9;
      --dark-text-secondary: #d6d3d1;
      --dark-sage: #6b8d85;
    }

    * { 
      margin: 0; 
      padding: 0; 
      box-sizing: border-box; 
    }
    
    html { 
      scroll-behavior: smooth; 
      font-size: clamp(14px, 1.5vw, 18px); 
    }
    
    body {
      font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
      background: linear-gradient(135deg, var(--primary-bg) 50%, var(--secondary-bg) 100%);
      color: var(--text-primary);
      line-height: 1.6;
      overflow-x: hidden;
    }

    body.dark-mode {
      background: linear-gradient(135deg, var(--dark-primary) 0%, var(--dark-secondary) 100%);
      color: white;
    }

    body.dark-mode * {
      color: white;
    }

    /* Loading Animation */
    .loader {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100vh;
      background: var(--primary-bg);
      display: flex;
      align-items: center;
      justify-content: center;
      z-index: 9999;
      transition: opacity 0.8s ease, visibility 0.8s ease;
    }

    .loader.fade-out {
      opacity: 0;
      visibility: hidden;
    }

    .spinner-elegant {
      width: 60px;
      height: 60px;
      border: 3px solid var(--accent-bg);
      border-top: 3px solid var(--sage-green);
      border-radius: 50%;
      animation: elegantSpin 2s cubic-bezier(0.4, 0, 0.2, 1) infinite;
    }

    @keyframes elegantSpin {
      0% { transform: rotate(0deg) scale(1); }
      50% { transform: rotate(180deg) scale(1.1); }
      100% { transform: rotate(360deg) scale(1); }
    }

    /* Sophisticated Header */
    header {
      position: fixed;
      top: 0;
      left: 0;
      right: 0;
      height: 80px;
      background: linear-gradient(to left, orange, lightpink);
      backdrop-filter: blur(20px) saturate(150%);
      border-bottom: 1px solid rgba(168, 162, 158, 0.1);
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 0 clamp(20px, 5vw, 60px);
      z-index: 1000;
      transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
    }

    body.dark-mode header {
      background: linear-gradient(to right, orange, lightpink);
      border-bottom: 1px solid rgba(68, 64, 60, 0.3);
    }

    .logo {
      font-family: 'Playfair Display', serif;
      font-size: clamp(1.2rem, 2vw, 1.8rem);
      font-weight: 700;
      color: var(--text-primary);
      letter-spacing: -0.02em;
    }

    body.dark-mode .logo {
      color: white;
    }

    body.dark-mode .logo h2 {
      color: white;
    }

    nav ul {
      display: flex;
      list-style: none;
      gap: clamp(15px, 3vw, 40px);
    }

    nav a {
      color: var(--text-secondary);
      text-decoration: none;
      font-weight: 500;
      font-size: 0.9rem;
      position: relative;
      transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
      letter-spacing: 0.01em;
    }

    nav a::after {
      content: '';
      position: absolute;
      bottom: -2px;
      left: 0;
      width: 0;
      height: 2px;
      background: var(--sage-green);
      transition: width 0.3s cubic-bezier(0.4, 0, 0.2, 1);
    }

    nav a:hover {
      color: var(--text-primary);
      transform: translateY(-1px);
    }

    nav a:hover::after,
    nav a.active::after {
      width: 100%;
    }

    body.dark-mode nav a {
      color: white;
    }

    body.dark-mode nav a:hover {
      color: white;
    }

    #theme-toggle {
      background: none;
      border: none;
      cursor: pointer;
      font-size: 1.5rem;
      padding: 8px;
      border-radius: 12px;
      transition: all 0.3s ease;
      margin-left: 20px;
    }

    #theme-toggle:hover {
      background: var(--accent-bg);
      transform: rotate(15deg);
    }

    /* Hero Section - Asymmetrical Design */
    .hero {
      min-height: 100vh;
      display: grid;
      grid-template-columns: 1fr 1fr;
      align-items: center;
      padding: 80px clamp(20px, 5vw, 60px) 0;
      position: relative;
      overflow: hidden;
    }

    .hero-content {
      z-index: 2;
      animation: slideInLeft 1.2s cubic-bezier(0.4, 0, 0.2, 1);
    }

    body.dark-mode .hero-content {
      color: white;
    }

    body.dark-mode .hero-content * {
      color: white !important;
    }

    .hero-visual {
      position: relative;
      height: 100vh;
      overflow: hidden;
      animation: slideInRight 1.2s cubic-bezier(0.4, 0, 0.2, 1);
    }

    .hero-slideshow {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      object-fit: cover;
      opacity: 0;
      transition: opacity 2s cubic-bezier(0.4, 0, 0.2, 1);
      filter: brightness(0.9) contrast(1.1);
    }

    .hero-slideshow.active {
      opacity: 1;
    }

    .hero h1 {
      font-family: 'Playfair Display', serif;
      font-size: clamp(2.5rem, 6vw, 4.5rem);
      font-weight: 700;
      line-height: 1.1;
      margin-bottom: 1.5rem;
      color: var(--text-primary);
      letter-spacing: -0.03em;
    }

    body.dark-mode .hero h1 {
      color: white;
    }

    .hero .subtitle {
      font-size: clamp(1.1rem, 2vw, 1.4rem);
      color: var(--text-secondary);
      margin-bottom: 2.5rem;
      font-weight: 300;
      letter-spacing: 0.02em;
    }

    body.dark-mode .hero .subtitle {
      color: white;
    }

    .cta-button {
      display: inline-flex;
      align-items: center;
      gap: 12px;
      background: var(--sage-green);
      color: white;
      padding: 16px 32px;
      border-radius: 50px;
      text-decoration: none;
      font-weight: 600;
      font-size: 1rem;
      transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
      box-shadow: 0 4px 20px rgba(132, 165, 157, 0.3);
    }

    .cta-button:hover {
      transform: translateY(-2px);
      box-shadow: 0 8px 30px rgba(132, 165, 157, 0.4);
      background: color-mix(in srgb, var(--sage-green) 90%, black 10%);
    }

    .scroll-indicator {
      position: absolute;
      bottom: 40px;
      left: 50%;
      transform: translateX(-50%);
      animation: bounce 2s infinite;
      font-size: 1.5rem;
      color: var(--text-muted);
    }

    @keyframes slideInLeft {
      from { opacity: 0; transform: translateX(-60px); }
      to { opacity: 1; transform: translateX(0); }
    }

    @keyframes slideInRight {
      from { opacity: 0; transform: translateX(60px); }
      to { opacity: 1; transform: translateX(0); }
    }

    @keyframes bounce {
      0%, 100% { transform: translateX(-50%) translateY(0); }
      50% { transform: translateX(-50%) translateY(-10px); }
    }

    /* Modern Section Styling */
    .section {
      padding: clamp(60px, 12vw, 120px) clamp(20px, 5vw, 60px);
      opacity: 0;
      transform: translateY(40px);
      transition: all 0.8s cubic-bezier(0.4, 0, 0.2, 1);
    }

    .section.visible {
      opacity: 1;
      transform: translateY(0);
    }

    .section-title {
      font-family: 'Playfair Display', serif;
      font-size: clamp(2rem, 4vw, 3rem);
      font-weight: 700;
      margin-bottom: clamp(30px, 6vw, 60px);
      text-align: center;
      color: var(--text-primary);
      letter-spacing: -0.02em;
    }

    body.dark-mode .section-title {
      color: white;
    }

    .section-content {
      max-width: 800px;
      margin: 0 auto;
      text-align: center;
      font-size: 1.1rem;
      color: var(--text-secondary);
      line-height: 1.8;
    }

    body.dark-mode .section-content {
      color: white;
    }

    body.dark-mode .section-content p {
      color: white;
    }

    /* Cards with Sophisticated Design */
    .cards-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
      gap: 30px;
      margin-top: 60px;
    }

    .card {
      background: rgba(255, 255, 255, 0.7);
      backdrop-filter: blur(20px);
      border-radius: 20px;
      padding: 40px 30px;
      text-align: center;
      transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
      border: 1px solid rgba(168, 162, 158, 0.1);
      position: relative;
      overflow: hidden;
    }

    .card::before {
      content: '';
      position: absolute;
      top: 0;
      left: 0;
      right: 0;
      height: 3px;
      background: linear-gradient(90deg, var(--sage-green), var(--warm-gray));
      transform: scaleX(0);
      transition: transform 0.4s cubic-bezier(0.4, 0, 0.2, 1);
    }

    .card:hover::before {
      transform: scaleX(1);
    }

    .card:hover {
      transform: translateY(-8px);
      box-shadow: 0 20px 60px rgba(0, 0, 0, 0.1);
      background: rgba(255, 255, 255, 0.9);
    }

    body.dark-mode .card {
      background: rgba(68, 64, 60, 0.3);
      border: 1px solid rgba(168, 162, 158, 0.2);
      color: white;
    }

    body.dark-mode .card * {
      color: white;
    }

    body.dark-mode .card:hover {
      background: rgba(68, 64, 60, 0.5);
      color: white;
    }

    .card-icon {
      font-size: 3rem;
      margin-bottom: 20px;
      display: block;
    }

    .card h3 {
      font-family: 'Playfair Display', serif;
      font-size: 1.5rem;
      margin-bottom: 15px;
      color: var(--text-primary);
    }

    body.dark-mode .card h3 {
      color: white;
    }

    /* Interactive Gallery */
    .gallery-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
      gap: 30px;
      margin-top: 60px;
    }

    .gallery-item {
      position: relative;
      border-radius: 16px;
      overflow: hidden;
      cursor: pointer;
      transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
      aspect-ratio: 4/3;
    }

    .gallery-item img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      transition: all 0.6s cubic-bezier(0.4, 0, 0.2, 1);
    }

    .gallery-item:hover {
      transform: translateY(-5px);
      box-shadow: 0 20px 40px rgba(0, 0, 0, 0.15);
    }

    .gallery-item:hover img {
      transform: scale(1.05);
    }

    /* Elegant Form Design */
    .booking-form {
      max-width: 600px;
      margin: 0 auto;
      background: rgba(255, 255, 255, 0.8);
      backdrop-filter: blur(20px);
      padding: 50px;
      border-radius: 24px;
      border: 1px solid rgba(168, 162, 158, 0.1);
    }

    body.dark-mode .booking-form {
      background: rgba(68, 64, 60, 0.5);
      border: 1px solid rgba(168, 162, 158, 0.3);
    }

    .form-group {
      margin-bottom: 25px;
    }

    .form-group label {
      display: block;
      margin-bottom: 8px;
      font-weight: 500;
      color: var(--text-primary);
      font-size: 0.95rem;
    }

    body.dark-mode .form-group label {
      color: white;
    }

    .form-group input,
    .form-group select,
    .form-group textarea {
      width: 100%;
      padding: 16px 20px;
      border: 2px solid var(--accent-bg);
      border-radius: 12px;
      font-size: 1rem;
      transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
      background: rgba(255, 255, 255, 0.9);
      font-family: inherit;
    }

    body.dark-mode .form-group input,
    body.dark-mode .form-group select,
    body.dark-mode .form-group textarea {
      background: rgba(68, 64, 60, 0.8);
      border: 2px solid var(--dark-accent);
      color: white;
    }

    body.dark-mode .form-group input::placeholder,
    body.dark-mode .form-group textarea::placeholder {
      color: rgba(255, 255, 255, 0.7);
    }

    .form-group input:focus,
    .form-group select:focus,
    .form-group textarea:focus {
      outline: none;
      border-color: var(--sage-green);
      box-shadow: 0 0 0 3px rgba(132, 165, 157, 0.1);
      transform: translateY(-1px);
    }

    .submit-btn {
      width: 100%;
      background: var(--sage-green);
      color: white;
      border: none;
      padding: 18px;
      border-radius: 12px;
      font-size: 1.1rem;
      font-weight: 600;
      cursor: pointer;
      transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
    }

    .submit-btn:hover {
      background: color-mix(in srgb, var(--sage-green) 90%, black 10%);
      transform: translateY(-2px);
      box-shadow: 0 8px 25px rgba(132, 165, 157, 0.3);
    }

    /* Footer */
    footer {
      background: var(--charcoal);
      color: var(--soft-white);
      text-align: center;
      padding: 60px 30px 40px;
      margin-top: 80px;
    }

    footer .quote {
      font-family: 'Playfair Display', serif;
      font-size: 1.3rem;
      font-style: italic;
      margin-bottom: 20px;
      color: var(--cream);
    }

    footer .contact-info {
      font-size: 1rem;
      color: var(--warm-gray);
      line-height: 1.6;
    }

    /* Lightbox */
    #lightbox {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: rgba(0, 0, 0, 0.9);
      display: none;
      align-items: center;
      justify-content: center;
      z-index: 10000;
      backdrop-filter: blur(10px);
    }

    #lightbox img {
      max-width: 90%;
      max-height: 80%;
      border-radius: 12px;
      box-shadow: 0 20px 60px rgba(0, 0, 0, 0.5);
    }

    /* Interactive SVG Floor Plan */
    .floorplan-container {
      max-width: 700px;
      margin: 0 auto;
      padding: 40px;
      background: rgba(255, 255, 255, 0.8);
      backdrop-filter: blur(20px);
      border-radius: 20px;
      border: 1px solid rgba(168, 162, 158, 0.1);
    }

    body.dark-mode .floorplan-container {
      background: rgba(68, 64, 60, 0.5);
      border: 1px solid rgba(168, 162, 158, 0.3);
    }

    .hall-area {
      transition: all 0.3s ease;
      cursor: pointer;
    }

    .hall-area:hover {
      opacity: 0.8;
      filter: brightness(1.1);
    }

    .hall-info {
      margin-top: 20px;
      padding: 15px;
      background: var(--accent-bg);
      border-radius: 10px;
      font-weight: 500;
      color: var(--text-primary);
      min-height: 50px;
      display: flex;
      align-items: center;
      justify-content: center;
    }

    body.dark-mode .hall-info {
      background: var(--dark-accent);
      color: white;
    }

    /* Responsive Design */
    @media (max-width: 768px) {
      .hero {
        grid-template-columns: 1fr;
        text-align: center;
        padding: 100px 20px 60px;
      }

      .hero-visual {
        height: 50vh;
        order: -1;
      }

      nav ul {
        display: none;
      }

      .section {
        padding: 60px 20px;
      }

      .cards-grid {
        grid-template-columns: 1fr;
        gap: 20px;
      }

      .booking-form {
        padding: 30px 20px;
        margin: 0 20px;
      }
    }

    /* Custom animations for enhanced UX */
    @keyframes fadeInUp {
      from {
        opacity: 0;
        transform: translateY(30px);
      }
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }

    .animate-in {
      animation: fadeInUp 0.8s cubic-bezier(0.4, 0, 0.2, 1) forwards;
    }

    /* Stagger animation delays */
    .stagger-1 { animation-delay: 0.1s; }
    .stagger-2 { animation-delay: 0.2s; }
    .stagger-3 { animation-delay: 0.3s; }
  </style>
</head>
<body>
  
  <!-- Elegant Loader -->
  <div id="loader" class="loader">
    <div class="spinner-elegant"></div>
  </div>

  <!-- Sophisticated Header -->
  <header>
    <div class="logo"><h2>New Rose Garden Hall</h2></div>
    <nav>
      <ul>
        <li><a href="#" class="active">Home</a></li>
        <li><a href="#about">About</a></li>
        <li><a href="#services">Services</a></li>
        <li><a href="#gallery">Gallery</a></li>
        <li><a href="#booking">Book Now</a></li>
        <li><a href="#contact">Contact</a></li>
      </ul>
    </nav>
    <button id="theme-toggle" title="Toggle Theme">🌙</button>
  </header>

  <!-- Hero Section -->
  <section class="hero">
    <div class="hero-content">
      <h1>Where Every Celebration<br>Blooms in Elegance</h1>
      <p class="subtitle">Experience the perfect blend of sophisticated ambiance and exceptional service for your most cherished moments.</p>
      <a href="#booking" class="cta-button">
        <span>Reserve Your Date</span>
        <span>→</span>
      </a>
    </div>
    <div class="hero-visual">
      <img src="rose 4.jpg" class="hero-slideshow active" alt="Elegant Wedding Setup">
      <img src="rose 2.jpg" class="hero-slideshow" alt="Luxury Indian Wedding Hall">
      <img src="rose 3.jpg" class="hero-slideshow" alt="Sophisticated Event Space">
    </div>
    <div class="scroll-indicator">⬇</div>
  </section>

  <!-- About Section -->
  <section id="about" class="section">
    <h2 class="section-title">About Rose Garden Hall</h2>
    <div class="section-content">
      <p>Nestled in the heart of Kilimanjaro, New Rose Garden Hall stands as a testament to timeless elegance and contemporary sophistication. Our venue seamlessly blends traditional charm with modern amenities, creating the perfect backdrop for life's most precious celebrations.</p>
    </div>
    <div class="cards-grid">
      <div class="card animate-in stagger-1">
        <span class="card-icon">🏛️</span>
        <h3>Architectural Excellence</h3>
        <p>Our stunning venue features soaring ceilings, elegant chandeliers, and thoughtfully designed spaces that accommodate both intimate gatherings and grand celebrations.</p>
      </div>
      <div class="card animate-in stagger-2">
        <span class="card-icon">✨</span>
        <h3>Exceptional Service</h3>
        <p>Our dedicated team of event professionals ensures every detail is meticulously planned and flawlessly executed, allowing you to focus on what matters most.</p>
      </div>
      <div class="card animate-in stagger-3">
        <span class="card-icon">🌹</span>
        <h3>Personalized Experience</h3>
        <p>Every event is unique, and we pride ourselves on creating bespoke experiences that reflect your personal style and vision.</p>
      </div>
    </div>
  </section>

  <!-- Services Section -->
  <section id="services" class="section">
    <h2 class="section-title">Our Premium Services</h2>
    <div class="section-content">
      <p>From intimate ceremonies to grand receptions, we offer comprehensive event services tailored to your specific needs and desires.</p>
    </div>
    <div class="cards-grid">
      <div class="card animate-in stagger-1">
        <span class="card-icon">💍</span>
        <h3>Wedding Celebrations</h3>
        <p>Create magical moments with our complete wedding packages, including ceremony setups, reception arrangements, and personalized décor.</p>
      </div>
      <div class="card animate-in stagger-2">
        <span class="card-icon">🎉</span>
        <h3>Corporate Events</h3>
        <p>Impress your clients and colleagues with professional event setups, state-of-the-art audio-visual equipment, and elegant catering services.</p>
      </div>
      <div class="card animate-in stagger-3">
        <span class="card-icon">🍽️</span>
        <h3>Gourmet Catering</h3>
        <p>Delight your guests with expertly crafted menus featuring local and international cuisine, prepared by our award-winning culinary team.</p>
      </div>
    </div>  
  </section>

  <!-- Interactive Floor Plan -->
  <section id="floorplan" class="section">
    <h2 class="section-title">Interactive Hall Layout</h2>
    <div class="floorplan-container">
      <svg viewBox="0 0 600 400" style="width:100%; height:auto;">
        <!-- Main Hall -->
        <image href="rose.jpg" x="50" y="50" width="500" height="200" preserveAspectRatio="xMidYMid slice"/>
        <rect x="50" y="50" width="500" height="200" fill="rgba(132, 165, 157, 0.2)" class="hall-area"
          data-name="Main Hall" data-capacity="500 guests" data-setup="Weddings • Galas • Large Celebrations"/>
        
        <!-- VIP Lounge -->
        <image href="https://images.unsplash.com/photo-1579254216547-a90bea451479?crop=entropy&cs=tinysrgb&fit=max&fm=jpg&ixid=M3w3NTAxMTZ8MHwxfHNlYXJjaHw1fHxlbGVnYW50JTIwZXZlbnQlMjBoYWxsJTIwd2VkZGluZyUyMHZlbnVlJTIwaW50ZXJpb3J8ZW58MHwwfHx8MTc1ODgyMjMzNnww&ixlib=rb-4.1.0&q=80&w=400" x="50" y="270" width="200" height="100" preserveAspectRatio="xMidYMid slice"/>
        <rect x="50" y="270" width="200" height="100" fill="rgba(132, 165, 157, 0.2)" class="hall-area"
          data-name="Exclusive VIP Lounge" data-capacity="50 guests" data-setup="Private Meetings • Intimate Gatherings"/>
        
        <!-- Garden Patio -->
        <image href="https://images.unsplash.com/photo-1733246582009-da345865f875?crop=entropy&cs=tinysrgb&fit=max&fm=jpg&ixid=M3w3NTAxMTZ8MHwxfHNlYXJjaHwxfHxiZWF1dGlmdWwlMjBnYXJkZW4lMjBwYXJ0eSUyMG91dGRvb3IlMjBjZXJlbW9ueXxlbnwwfDB8fHwxNzU4ODIyMzM2fDA&ixlib=rb-4.1.0&q=80&w=400" x="270" y="270" width="280" height="100" preserveAspectRatio="xMidYMid slice"/>
        <rect x="270" y="270" width="280" height="100" fill="rgba(132, 165, 157, 0.2)" class="hall-area"
          data-name="Rose Garden Patio" data-capacity="150 guests" data-setup="Outdoor Ceremonies • Garden Parties"/>
      </svg>
      <div id="hallInfo" class="hall-info">Hover over different areas to explore our spaces</div>
    </div>
  </section>

  <!-- Gallery Section -->
  <section id="gallery" class="section">
    <h2 class="section-title">Event Gallery</h2>
    <div class="gallery-grid">
      <div class="gallery-item animate-in stagger-1">
        <img src="https://images.unsplash.com/photo-1624763149686-1893acf73092?crop=entropy&cs=tinysrgb&fit=max&fm=jpg&ixid=M3w3NTAxMTZ8MHwxfHNlYXJjaHwyfHxsdXh1cnklMjBiYW5xdWV0JTIwaGFsbCUyMGVsZWdhbnQlMjByZWNlcHRpb258ZW58MHwwfHx8MTc1ODgyMjMzNnww&ixlib=rb-4.1.0&q=80&w=400" alt="Elegant Banquet Setup">
      </div>
      <div class="gallery-item animate-in stagger-2">
        <img src="https://images.unsplash.com/photo-1750277116749-bc104a98c143?crop=entropy&cs=tinysrgb&fit=max&fm=jpg&ixid=M3w3NTAxMTZ8MHwxfHNlYXJjaHwzfHxsdXh1cnklMjBiYW5xdWV0JTIwaGFsbCUyMGVsZWdhbnQlMjByZWNlcHRpb258ZW58MHwwfHx8MTc1ODgyMjMzNnww&ixlib=rb-4.1.0&q=80&w=400" alt="Luxury Table Setting">
      </div>
      <div class="gallery-item animate-in stagger-3">
        <img src="https://images.unsplash.com/photo-1670336423329-3dfbcd081b16?crop=entropy&cs=tinysrgb&fit=max&fm=jpg&ixid=M3w3NTAxMTZ8MHwxfHNlYXJjaHwyfHxiZWF1dGlmdWwlMjBnYXJkZW4lMjBwYXJ0eSUyMG91dGRvb3IlMjBjZXJlbW9ueXxlbnwwfDB8fHwxNzU4ODIyMzM2fDA&ixlib=rb-4.1.0&q=80&w=400" alt="Garden Ceremony Setup">
      </div>
    </div>
  </section>

  <!-- Booking Section -->
  <section id="booking" class="section">
    <h2 class="section-title">Reserve Your Special Day</h2>
    <form id="bookingForm" class="booking-form">
      <div class="form-group">
        <label for="name">Full Name</label>
        <input type="text" id="name" name="name" required placeholder="Enter your full name">
      </div>
      <div class="form-group">
        <label for="email">Email Address</label>
        <input type="email" id="email" name="email" required placeholder="your.email@example.com">
      </div>
      <div class="form-group">
        <label for="phone">Phone Number</label>
        <input type="tel" id="phone" name="phone" required placeholder="+255 756 715 315">
      </div>
      <div class="form-group">
        <label for="eventDate">Preferred Date</label>
        <input type="date" id="eventDate" name="eventDate" required>
      </div>
      <div class="form-group">
        <label for="hallSelect">Select Venue Space</label>
        <select id="hallSelect" name="hallSelect" required>
          <option value="">Choose your preferred space</option>
          <option value="Grand Ballroom">Grand Ballroom (500 guests)</option>
          <option value="VIP Lounge">Exclusive VIP Lounge (50 guests)</option>
          <option value="Garden Patio">Rose Garden Patio (150 guests)</option>
        </select>
      </div>
      <div class="form-group">
        <label for="eventDetails">Event Details</label>
        <textarea id="eventDetails" name="eventDetails" rows="4" required placeholder="Please describe your event, number of guests, and any special requirements..."></textarea>
      </div>
      <button type="submit" class="submit-btn">Submit Booking Request</button>
    </form>
  </section>

  <section id="contact" class="section">
    <h2 class="section-title">Get in Touch</h2>
    <div class="section-content">
      <p><strong>Email:</strong> rosegarden@gmail.com</p>
      <p><strong>Phone:</strong> +255 756 715 315</p>
      <p><strong>Address:</strong> Kilimanjaro, Tanzania</p>
      <p style="margin-top: 30px;">We're here to help make your special day unforgettable. Contact us today to schedule a private venue tour.</p>
    </div>
  </section>

  <footer>
    <p class="quote">"Where every celebration blooms in elegance."</p>
    <div class="contact-info">
      <p>📍 Kilimanjaro, Tanzania | 📧 rosegarden@gmail.com | 📞 +255 756 715 315</p>
      <p style="margin-top: 15px; font-size: 0.9rem; opacity: 0.8;">© 2024 New Rose Garden Hall. Creating memorable moments since 2010.</p>
    </div>
  </footer>

  <div id="lightbox"><img src=""rose 3.jpg alt="Enlarged view"></div>

  <script>
    // Enhanced loader with smoother transition
    window.addEventListener('load', () => {
      const loader = document.getElementById('loader');
      setTimeout(() => {
        loader.classList.add('fade-out');
      }, 800);
    });

    // Sophisticated theme toggle
    const themeToggle = document.getElementById('theme-toggle');
    const body = document.body;

    // Initialize theme
    const savedTheme = localStorage.getItem('theme');
    const prefersDark = window.matchMedia('(prefers-color-scheme: dark)').matches;

    if (savedTheme === 'dark' || (!savedTheme && prefersDark)) {
      body.classList.add('dark-mode');
      themeToggle.textContent = '☀️';
    }

    themeToggle.addEventListener('click', () => {
      body.classList.toggle('dark-mode');
      const isDark = body.classList.contains('dark-mode');
      themeToggle.textContent = isDark ? '☀️' : '🌙';
      localStorage.setItem('theme', isDark ? 'dark' : 'light');
    });

    // Advanced scroll animations
    const observerOptions = {
      threshold: 0.15,
      rootMargin: '0px 0px -100px 0px'
    };

    const observer = new IntersectionObserver((entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          entry.target.classList.add('visible');
          
          // Trigger staggered animations for cards
          const animatedElements = entry.target.querySelectorAll('.animate-in');
          animatedElements.forEach((el, index) => {
            setTimeout(() => {
              el.style.opacity = '1';
              el.style.transform = 'translateY(0)';
            }, index * 150);
          });
        }
      });
    }, observerOptions);

    // Observe all sections
    document.querySelectorAll('.section').forEach(section => {
      observer.observe(section);
    });

    // Initialize animate-in elements
    document.querySelectorAll('.animate-in').forEach(el => {
      el.style.opacity = '0';
      el.style.transform = 'translateY(30px)';
      el.style.transition = 'all 0.8s cubic-bezier(0.4, 0, 0.2, 1)';
    });

    // Enhanced slideshow with smoother transitions
    const slides = document.querySelectorAll('.hero-slideshow');
    let currentSlide = 0;

    function nextSlide() {
      slides[currentSlide].classList.remove('active');
      currentSlide = (currentSlide + 1) % slides.length;
      slides[currentSlide].classList.add('active');
    }

    // Start slideshow after a delay
    setTimeout(() => {
      setInterval(nextSlide, 6000);
    }, 3000);

    // Gallery lightbox with smooth animation
    const galleryItems = document.querySelectorAll('.gallery-item img');
    const lightbox = document.getElementById('lightbox');
    const lightboxImg = lightbox.querySelector('img');

    galleryItems.forEach(img => {
      img.addEventListener('click', () => {
        lightboxImg.src = img.src;
        lightbox.style.display = 'flex';
        setTimeout(() => {
          lightbox.style.opacity = '1';
        }, 10);
      });
    });

    lightbox.addEventListener('click', (e) => {
      if (e.target === lightbox) {
        lightbox.style.opacity = '0';
        setTimeout(() => {
          lightbox.style.display = 'none';
        }, 300);
      }
    });

    // Interactive floor plan
    const hallAreas = document.querySelectorAll('.hall-area');
    const hallInfo = document.getElementById('hallInfo');

    hallAreas.forEach(area => {
      area.addEventListener('mouseenter', () => {
        const name = area.dataset.name;
        const capacity = area.dataset.capacity;
        const setup = area.dataset.setup;
        hallInfo.innerHTML = `<strong>${name}</strong><br>Capacity: ${capacity}<br>Ideal for: ${setup}`;
      });

      area.addEventListener('mouseleave', () => {
        hallInfo.textContent = 'Hover over different areas to explore our spaces';
      });
    });

    // Enhanced form handling
    const bookingForm = document.getElementById('bookingForm');
    const hallSelect = document.getElementById('hallSelect');

    bookingForm.addEventListener('submit', (e) => {
      e.preventDefault();
      
      // Simple form validation and success message
      const formData = new FormData(bookingForm);
      const data = Object.fromEntries(formData);
      
      // Simulate form submission
      const submitBtn = bookingForm.querySelector('.submit-btn');
      const originalText = submitBtn.textContent;
      
      submitBtn.textContent = 'Submitting...';
      submitBtn.disabled = true;
      
      setTimeout(() => {
        alert(`Thank you, ${data.name}! Your booking request for ${data.hallSelect} on ${data.eventDate} has been submitted. We'll contact you within 24 hours.`);
        bookingForm.reset();
        submitBtn.textContent = originalText;
        submitBtn.disabled = false;
      }, 2000);
    });

    // Smooth scrolling for navigation links
    document.querySelectorAll('nav a[href^="#"]').forEach(link => {
      link.addEventListener('click', (e) => {
        e.preventDefault();
        const targetId = link.getAttribute('href');
        const targetSection = document.querySelector(targetId);
        
        if (targetSection) {
          targetSection.scrollIntoView({
            behavior: 'smooth',
            block: 'start'
          });
        }
      });
    });

    // Update active navigation link on scroll
    window.addEventListener('scroll', () => {
      const sections = document.querySelectorAll('section[id]');
      const navLinks = document.querySelectorAll('nav a[href^="#"]');
      
      let currentSection = '';
      
      sections.forEach(section => {
        const rect = section.getBoundingClientRect();
        if (rect.top <= 100 && rect.bottom >= 100) {
          currentSection = section.id;
        }
      });
      
      navLinks.forEach(link => {
        link.classList.remove('active');
        if (link.getAttribute('href') === `#${currentSection}`) {
          link.classList.add('active');
        }
      });
    });
  </script>
</body>
</html>
