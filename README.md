<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Vimate Group</title>
  <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@600;400&display=swap" rel="stylesheet">
  <style>
    :root {
      --primary: #1e3a5c;
      --secondary: #00bfae;
      --background: #f4f8fb;
      --accent: #f9fafc;
      --text: #222;
      --white: #fff;
      --shadow: 0 8px 32px 0 rgba(30,58,92,0.10);
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      font-family: 'Montserrat', Arial, sans-serif;
      background: var(--background);
      color: var(--text);
      min-height: 100vh;
    }

    header {
      background: linear-gradient(90deg, var(--primary) 60%, var(--secondary) 100%);
      color: var(--white);
      padding: 3rem 1rem 2rem 1rem;
      text-align: center;
      box-shadow: var(--shadow);
      position: relative;
      width: 100vw;
      left: 50%;
      right: 50%;
      margin-left: -50vw;
      margin-right: -50vw;
    }

    header h1 {
      font-size: 3.2rem;
      letter-spacing: 2px;
      margin-bottom: 0.7rem;
      font-weight: 700;
    }

    header p {
      font-size: 1.5rem;
      font-weight: 400;
      opacity: 0.95;
      margin-bottom: 0.5rem;
    }

    nav {
      background: var(--white);
      box-shadow: 0 2px 8px rgba(30,58,92,0.05);
      display: flex;
      justify-content: center;
      align-items: center;
      gap: 2.5rem;
      padding: 1.3rem 0;
      position: sticky;
      top: 0;
      z-index: 20;
      animation: navFadeIn 1.2s;
      width: 100vw;
      left: 50%;
      right: 50%;
      margin-left: -50vw;
      margin-right: -50vw;
    }

    nav a {
      color: var(--primary);
      text-decoration: none;
      font-weight: 600;
      font-size: 1.15rem;
      position: relative;
      transition: color 0.2s;
      padding: 0.2rem 0.7rem;
      letter-spacing: 0.5px;
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

    nav a:hover {
      color: var(--secondary);
    }

    nav a:hover::after {
      width: 100%;
    }

    .container {
      width: 96vw;
      max-width: 1700px;
      margin: 3rem auto 2rem auto;
      padding: 3rem 3vw 3rem 3vw;
      background: var(--accent);
      border-radius: 12px;
      box-shadow: var(--shadow);
      animation: fadeIn 1.2s;
      min-height: 60vh;
    }

    section {
      margin-bottom: 3.5rem;
    }

    h2 {
      color: var(--primary);
      font-size: 2.3rem;
      margin-bottom: 1.2rem;
      letter-spacing: 1.2px;
      font-weight: 700;
    }

    /* About */
    #about p {
      font-size: 1.22rem;
      line-height: 1.8;
      color: #333;
      margin-bottom: 0.5rem;
    }

    /* Services */
    .services-list {
      display: flex;
      flex-wrap: wrap;
      gap: 2.5rem;
      justify-content: space-between;
      margin-top: 2rem;
    }

    .service-card {
      background: var(--white);
      border-radius: 8px;
      box-shadow: 0 4px 24px 0 rgba(30,58,92,0.07);
      padding: 2.2rem 1.5rem 2rem 1.5rem;
      flex: 1 1 320px;
      max-width: 360px;
      min-width: 240px;
      text-align: center;
      transition: transform 0.2s, box-shadow 0.2s;
      position: relative;
      overflow: hidden;
      margin-bottom: 1.5rem;
    }

    .service-card:hover {
      transform: translateY(-10px) scale(1.035);
      box-shadow: 0 12px 36px 0 rgba(0,191,174,0.14);
      background: linear-gradient(120deg, #f2fcfb 70%, #e3f8f7 100%);
    }

    .service-icon {
      font-size: 2.7rem;
      color: var(--secondary);
      margin-bottom: 1.1rem;
      display: block;
    }

    .service-title {
      font-size: 1.23rem;
      font-weight: 700;
      margin-bottom: 0.6rem;
      color: var(--primary);
      letter-spacing: 0.5px;
    }

    .service-desc {
      font-size: 1.07rem;
      color: #444;
      opacity: 0.92;
      line-height: 1.5;
    }

    /* Contact */
    #contact p {
      font-size: 1.13rem;
      margin-bottom: 0.6rem;
      color: #333;
    }

    #contact a {
      color: var(--secondary);
      text-decoration: underline;
      transition: color 0.2s;
    }

    #contact a:hover {
      color: var(--primary);
    }

    /* Footer */
    footer {
      background: linear-gradient(90deg, var(--primary) 60%, var(--secondary) 100%);
      color: var(--white);
      text-align: center;
      padding: 1.4rem 0;
      font-size: 1.1rem;
      letter-spacing: 0.7px;
      position: relative;
      margin-top: 2.5rem;
      width: 100vw;
      left: 50%;
      right: 50%;
      margin-left: -50vw;
      margin-right: -50vw;
    }

    /* Animations */
    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(30px);}
      to { opacity: 1; transform: none;}
    }
    @keyframes navFadeIn {
      from { opacity: 0; transform: translateY(-30px);}
      to { opacity: 1; transform: none;}
    }

    /* Responsive */
    @media (max-width: 1200px) {
      .container {
        width: 99vw;
        max-width: 100vw;
        padding: 2.5rem 1vw;
      }
      .services-list {
        gap: 1.5rem;
      }
    }
    @media (max-width: 900px) {
      .container {
        padding: 1.5rem 0.5vw;
      }
      .services-list {
        flex-direction: column;
        align-items: center;
        gap: 1.2rem;
      }
      .service-card {
        max-width: 98vw;
      }
    }
    @media (max-width: 700px) {
      header h1 {
        font-size: 2.1rem;
      }
      h2 {
        font-size: 1.4rem;
      }
      .container {
        padding: 1rem 0.1vw;
        border-radius: 0;
      }
      nav {
        gap: 1rem;
        font-size: 1rem;
      }
    }
    @media (max-width: 500px) {
      header {
        padding: 2rem 0.2rem 1.2rem 0.2rem;
      }
      nav {
        padding: 0.7rem 0;
      }
      .container {
        padding: 0.5rem 0;
      }
    }
  </style>
</head>
<body>
  <header>
    <h1>Vimate Group</h1>
    <p>Your Trusted Partner in Business Solutions</p>
  </header>
  <nav>
    <a href="#about">About</a>
    <a href="#services">Services</a>
    <a href="#contact">Contact</a>
  </nav>
  <div class="container">
    <section id="about">
      <h2>About Us</h2>
      <p>
        <b>Vimate Group</b> is committed to delivering innovative, tailor-made business solutions that empower organizations to achieve their highest potential. With a focus on quality, integrity, and customer satisfaction, we help clients succeed in a rapidly changing world. Our expert team brings together years of experience across industries to create measurable impact for your business.
      </p>
    </section>
    <section id="services">
      <h2>Our Services</h2>
      <div class="services-list">
        <div class="service-card">
          <span class="service-icon">💼</span>
          <div class="service-title">Business Consulting</div>
          <div class="service-desc">
            Strategic guidance and actionable insights to drive growth, optimize operations, and elevate your business performance.
          </div>
        </div>
        <div class="service-card">
          <span class="service-icon">💻</span>
          <div class="service-title">Technology Solutions</div>
          <div class="service-desc">
            Cutting-edge digital solutions, from custom software to IT infrastructure, tailored to your unique business needs.
          </div>
        </div>
        <div class="service-card">
          <span class="service-icon">📈</span>
          <div class="service-title">Market Analysis</div>
          <div class="service-desc">
            In-depth market research and analytics to empower informed decision-making and uncover new growth opportunities.
          </div>
        </div>
        <div class="service-card">
          <span class="service-icon">🗂️</span>
          <div class="service-title">Project Management</div>
          <div class="service-desc">
            End-to-end project planning and execution, ensuring timely delivery, quality, and alignment with your business goals.
          </div>
        </div>
      </div>
    </section>
    <section id="contact">
      <h2>Contact Us</h2>
      <p>Email: <a href="mailto:info@vimategroup.com">info@vimategroup.com</a></p>
      <p>Phone: +91-XXXXXXXXXX</p>
      <p>Address: 123 Business Avenue, Mumbai, India</p>
    </section>
  </div>
  <footer>
    &copy; 2025 Vimate Group. All rights reserved.
  </footer>
</body>
</html>
