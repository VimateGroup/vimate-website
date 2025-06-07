<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Vimate Group</title>
  <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@600;400&display=swap" rel="stylesheet">
  <style>
    :root {
      --primary: #1e3a5c;
      --secondary: #00bfae;
      --background: #f4f8fb;
      --accent: #fff;
      --text: #222;
      --shadow: 0 8px 32px 0 rgba(30,58,92,0.10);
      --container-width: 1100px;
      --radius: 14px;
    }
    * { box-sizing: border-box; margin: 0; padding: 0; }
    body {
      font-family: 'Montserrat', Arial, sans-serif;
      background: var(--background);
      color: var(--text);
      min-height: 100vh;
    }
    header {
      background: linear-gradient(90deg, var(--primary) 60%, var(--secondary) 100%);
      color: var(--accent);
      padding: 2.5rem 0 2rem 0;
      text-align: center;
      box-shadow: var(--shadow);
    }
    header h1 {
      font-size: 2.4rem;
      letter-spacing: 1px;
      margin-bottom: 0.6rem;
      font-weight: 700;
    }
    header p {
      font-size: 1.18rem;
      font-weight: 400;
      opacity: 0.96;
    }
    .nav-wrapper {
      background: var(--accent);
      box-shadow: 0 2px 8px rgba(30,58,92,0.05);
    }
    nav {
      max-width: var(--container-width);
      margin: 0 auto;
      display: flex;
      justify-content: center;
      align-items: center;
      gap: 2rem;
      padding: 1.1rem 0;
    }
    nav a {
      color: var(--primary);
      text-decoration: none;
      font-weight: 600;
      font-size: 1.08rem;
      position: relative;
      transition: color 0.2s;
      padding: 0.2rem 0.7rem;
      letter-spacing: 0.5px;
      cursor: pointer;
      border-radius: 5px;
    }
    nav a.active,
    nav a:hover {
      color: var(--secondary);
      background: #f0f9f8;
    }
    nav a::after {
      content: '';
      display: block;
      width: 0;
      height: 2px;
      background: var(--secondary);
      transition: width 0.3s;
      margin: 0 auto;
      border-radius: 2px;
    }
    nav a.active::after,
    nav a:hover::after {
      width: 100%;
    }
    .container {
      max-width: var(--container-width);
      margin: 2.5rem auto 2rem auto;
      padding: 2.5rem 2rem 2.5rem 2rem;
      background: var(--accent);
      border-radius: var(--radius);
      box-shadow: var(--shadow);
      min-height: 60vh;
      transition: box-shadow 0.2s;
    }
    section {
      display: none;
      animation: fadeIn 0.7s;
    }
    section.active {
      display: block;
    }
    h2 {
      color: var(--primary);
      font-size: 2rem;
      margin-bottom: 1.1rem;
      letter-spacing: 1px;
      font-weight: 700;
      text-align: left;
    }
    /* Home Highlights */
    .highlights {
      display: flex;
      flex-wrap: wrap;
      gap: 1.5rem;
      margin-bottom: 1.5rem;
      justify-content: flex-start;
    }
    .highlight-card {
      background: #f6fafd;
      border-radius: 8px;
      box-shadow: 0 2px 10px 0 rgba(30,58,92,0.04);
      padding: 1.1rem 1.4rem;
      min-width: 180px;
      max-width: 260px;
      flex: 1 1 180px;
      font-size: 1.02rem;
      color: var(--primary);
      font-weight: 600;
      display: flex;
      align-items: center;
      gap: 0.7rem;
    }
    .highlight-card span {
      font-size: 1.5rem;
      color: var(--secondary);
    }
    .cta {
      margin: 2.2rem 0 0 0;
      font-size: 1.23rem;
      color: var(--secondary);
      font-weight: 700;
      letter-spacing: 1px;
      text-align: center;
    }
    /* Services */
    .services-list {
      display: flex;
      flex-wrap: wrap;
      gap: 1.5rem;
      justify-content: flex-start;
      margin-top: 1.5rem;
    }
    .service-card {
      background: #f6fafd;
      border-radius: 8px;
      box-shadow: 0 2px 10px 0 rgba(30,58,92,0.04);
      padding: 1.7rem 1.2rem 1.5rem 1.2rem;
      flex: 1 1 240px;
      max-width: 270px;
      min-width: 180px;
      text-align: left;
      transition: transform 0.2s, box-shadow 0.2s;
      position: relative;
      margin-bottom: 0.5rem;
      display: flex;
      flex-direction: column;
      align-items: flex-start;
      gap: 0.5rem;
    }
    .service-card:hover {
      transform: translateY(-6px) scale(1.025);
      box-shadow: 0 8px 24px 0 rgba(0,191,174,0.10);
      background: linear-gradient(120deg, #f2fcfb 70%, #e3f8f7 100%);
    }
    .service-icon {
      font-size: 2rem;
      color: var(--secondary);
      margin-bottom: 0.5rem;
      display: block;
    }
    .service-title {
      font-size: 1.09rem;
      font-weight: 700;
      margin-bottom: 0.2rem;
      color: var(--primary);
      letter-spacing: 0.2px;
    }
    .service-desc {
      font-size: 0.98rem;
      color: #444;
      opacity: 0.92;
      line-height: 1.5;
      font-weight: 400;
    }
    /* About */
    .about-list {
      margin-top: 1rem;
      margin-bottom: 1.5rem;
      padding-left: 1.2rem;
      color: #333;
      font-size: 1.06rem;
    }
    .about-list li {
      margin-bottom: 0.6rem;
      line-height: 1.6;
    }
    /* Locations */
    .locations-list {
      margin-top: 1.2rem;
      display: flex;
      flex-wrap: wrap;
      gap: 1rem;
      font-size: 1.01rem;
      justify-content: flex-start;
    }
    .location-card {
      background: #f6fafd;
      border-radius: 8px;
      box-shadow: 0 2px 10px 0 rgba(30,58,92,0.04);
      padding: 0.9rem 1.2rem;
      min-width: 120px;
      max-width: 180px;
      flex: 1 1 120px;
      color: var(--primary);
      font-weight: 600;
      display: flex;
      align-items: center;
      gap: 0.6rem;
    }
    .location-card span {
      font-size: 1.2rem;
      color: var(--secondary);
    }
    /* Contact */
    .contact-details {
      margin-bottom: 1.3rem;
      font-size: 1.06rem;
      color: #333;
    }
    .contact-details p {
      margin-bottom: 0.4rem;
    }
    form {
      background: #f6fafd;
      border-radius: 8px;
      padding: 1.5rem 1rem;
      max-width: 380px;
      margin: 0 auto;
      box-shadow: 0 2px 10px 0 rgba(30,58,92,0.04);
      display: flex;
      flex-direction: column;
      gap: 1rem;
    }
    label {
      font-weight: 600;
      color: var(--primary);
      margin-bottom: 0.2rem;
      font-size: 0.98rem;
    }
    input, textarea {
      padding: 0.7rem;
      border: 1px solid #d1e6ee;
      border-radius: 5px;
      font-size: 1rem;
      font-family: inherit;
      background: #f7fafc;
      transition: border 0.2s;
    }
    input:focus, textarea:focus {
      border: 1.5px solid var(--secondary);
      outline: none;
    }
    textarea {
      min-height: 70px;
      resize: vertical;
    }
    button {
      background: var(--secondary);
      color: var(--accent);
      border: none;
      border-radius: 5px;
      padding: 0.8rem 0;
      font-size: 1.02rem;
      font-weight: 700;
      cursor: pointer;
      transition: background 0.2s;
      margin-top: 0.2rem;
      letter-spacing: 0.5px;
    }
    button:hover {
      background: var(--primary);
    }
    .form-success {
      color: var(--secondary);
      font-weight: 600;
      margin-top: 1rem;
      text-align: center;
      font-size: 1rem;
    }
    /* Footer */
    footer {
      background: linear-gradient(90deg, var(--primary) 60%, var(--secondary) 100%);
      color: var(--accent);
      text-align: center;
      padding: 1.1rem 0;
      font-size: 1rem;
      letter-spacing: 0.5px;
      margin-top: 2rem;
    }
    /* Animations */
    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(20px);}
      to { opacity: 1; transform: none;}
    }
    /* Responsive */
    @media (max-width: 1200px) {
      .container { max-width: 98vw; padding: 2rem 1vw; }
      nav { max-width: 98vw; }
    }
    @media (max-width: 900px) {
      .container { padding: 1.2rem 0.5vw; }
      .services-list, .highlights, .locations-list {
        flex-direction: column;
        align-items: flex-start;
        gap: 1rem;
      }
      .service-card, .highlight-card, .location-card { max-width: 100%; }
    }
    @media (max-width: 700px) {
      header h1 { font-size: 1.5rem; }
      h2 { font-size: 1.1rem; }
      .container { padding: 0.7rem 0.1vw; border-radius: 0; }
      nav { gap: 0.7rem; font-size: 0.95rem; }
    }
    @media (max-width: 500px) {
      header { padding: 1.1rem 0.2rem 0.7rem 0.2rem; }
      nav { padding: 0.5rem 0; }
      .container { padding: 0.3rem 0; }
      form { padding: 0.7rem 0.3rem; }
    }
  </style>
</head>
<body>
  <header>
    <h1>Vimate Group</h1>
    <p>India’s Trusted HR & Labour Compliance Partner</p>
  </header>
  <div class="nav-wrapper">
    <nav>
      <a class="active" data-page="home">Home</a>
      <a data-page="services">Services</a>
      <a data-page="about">About</a>
      <a data-page="locations">Locations</a>
      <a data-page="contact">Contact</a>
    </nav>
  </div>
  <div class="container">
    <!-- Home Page -->
    <section id="home" class="active">
      <h2>Welcome to Vimate Group</h2>
      <div class="highlights">
        <div class="highlight-card"><span>🌐</span> Pan-India Presence</div>
        <div class="highlight-card"><span>🏢</span> Mumbai HQ & Offices Nationwide</div>
        <div class="highlight-card"><span>🤝</span> 100+ Clients Across Sectors</div>
      </div>
      <div class="highlights">
        <div class="highlight-card"><span>🔍</span> Recruitment</div>
        <div class="highlight-card"><span>💳</span> Payroll</div>
        <div class="highlight-card"><span>📝</span> Compliance</div>
        <div class="highlight-card"><span>👷‍♂️</span> Manpower Outsourcing</div>
      </div>
      <div class="cta">Empowering Indian Workplaces with Smart HR Solutions.</div>
    </section>
    <!-- Services Page -->
    <section id="services">
      <h2>Our Services</h2>
      <div class="services-list">
        <div class="service-card">
          <span class="service-icon">🔍</span>
          <div class="service-title">Permanent Recruitment</div>
          <div class="service-desc">
            Skilled talent hiring across industries: manufacturing, retail, IT, pharma, and more.
          </div>
        </div>
        <div class="service-card">
          <span class="service-icon">👷‍♂️</span>
          <div class="service-title">Manpower Staffing</div>
          <div class="service-desc">
            Contract labour and workforce outsourcing PAN India, with compliance guaranteed.
          </div>
        </div>
        <div class="service-card">
          <span class="service-icon">💳</span>
          <div class="service-title">Payroll Services</div>
          <div class="service-desc">
            Full payroll management: statutory compliance, timely salary processing.
          </div>
        </div>
        <div class="service-card">
          <span class="service-icon">📝</span>
          <div class="service-title">Labour Compliance Management</div>
          <div class="service-desc">
            Licensing, registrations, audits, and legal adherence for all Indian states.
          </div>
        </div>
        <div class="service-card">
          <span class="service-icon">💡</span>
          <div class="service-title">Additional Services</div>
          <div class="service-desc">
            HR advisory, employee engagement, and training solutions.
          </div>
        </div>
      </div>
    </section>
    <!-- About Page -->
    <section id="about">
      <h2>About Us</h2>
      <ul class="about-list">
        <li><strong>Vision:</strong> To be India’s most trusted compliance-first HR partner.</li>
        <li>Founded with a mission to bridge HR gaps in Indian industries.</li>
        <li>Combining on-ground experience, technology, and statutory expertise.</li>
        <li>Serving manufacturing, logistics, retail, IT, pharma, and more.</li>
        <li>Mumbai-based with a delivery network across India.</li>
      </ul>
    </section>
    <!-- Locations Page -->
    <section id="locations">
      <h2>Our Locations & Coverage</h2>
      <div class="contact-details">
        <p><b>Headquartered:</b> Mumbai</p>
        <p>Pan-India delivery & service network covering:</p>
      </div>
      <div class="locations-list">
        <div class="location-card"><span>📍</span> Gujarat</div>
        <div class="location-card"><span>📍</span> Maharashtra</div>
        <div class="location-card"><span>📍</span> Karnataka</div>
        <div class="location-card"><span>📍</span> Tamil Nadu</div>
        <div class="location-card"><span>📍</span> Delhi NCR</div>
        <div class="location-card"><span>📍</span> Telangana</div>
        <div class="location-card"><span>📍</span> West Bengal</div>
        <div class="location-card"><span>📍</span> ...and more</div>
      </div>
      <div class="cta" style="margin-top:2rem;">
        We expertly handle multi-location, multi-state compliance and staffing needs.
      </div>
    </section>
    <!-- Contact Page -->
    <section id="contact">
      <h2>Contact Us</h2>
      <div class="contact-details">
        <p><b>Phone:</b> +91-XXXXXXXXXX</p>
        <p><b>Email:</b> <a href="mailto:info@vimategroup.com">info@vimategroup.com</a></p>
        <p>Get in touch with our HR experts today!</p>
      </div>
      <form id="contactForm" autocomplete="off">
        <div>
          <label for="name">Name</label>
          <input type="text" id="name" name="name" required placeholder="Your Name">
        </div>
        <div>
          <label for="email">Email</label>
          <input type="email" id="email" name="email" required placeholder="you@email.com">
        </div>
        <div>
          <label for="message">Message</label>
          <textarea id="message" name="message" required placeholder="How can we help you?"></textarea>
        </div>
        <button type="submit">Send Message</button>
        <div class="form-success" id="formSuccess" style="display:none;">Thank you! We'll get back to you soon.</div>
      </form>
    </section>
  </div>
  <footer>
    &copy; 2025 Vimate Group. All rights reserved.
  </footer>
  <script>
    // Navigation logic for multi-page effect
    const navLinks = document.querySelectorAll('nav a');
    const sections = document.querySelectorAll('.container section');
    navLinks.forEach(link => {
      link.addEventListener('click', () => {
        navLinks.forEach(l => l.classList.remove('active'));
        sections.forEach(sec => sec.classList.remove('active'));
        link.classList.add('active');
        document.getElementById(link.dataset.page).classList.add('active');
        document.querySelector('.container').scrollIntoView({behavior: 'smooth'});
      });
    });
    // Contact form fake submit
    document.getElementById('contactForm').addEventListener('submit', function(e){
      e.preventDefault();
      document.getElementById('formSuccess').style.display = 'block';
      this.reset();
      setTimeout(() => {
        document.getElementById('formSuccess').style.display = 'none';
      }, 4000);
    });
  </script>
</body>
</html>
